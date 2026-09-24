# autoresearch

This is an experiment to have the LLM do its own research.

## Setup

Work with the user to:

1. **Agree on a run tag** based on today's date (e.g. `mar5`); `autoresearch/<tag>` must not already exist. Create the branch from `main`.
2. **Read the in-scope files**: `README.md` and `train_gpt.py` — the pipeline script, what gets submitted and what measures T.
3. **Verify deps and data**: `uv sync` and `uv run python data/cached_fineweb10B.py 45` (190 steps of data per shard).
4. **Confirm and go.**

## Experimentation

Each experiment is two runs on the 8xH100 box:

```
WAN_MODE=off uv run torchrun --standalone --nproc_per_node=8 train_gpt.py > run1.log 2>&1    # run 1: loss run (~80 minutes; or a DDP twin, see below)
WAN_MODE=on  uv run torchrun --standalone --nproc_per_node=8 train_gpt.py > run2.log 2>&1    # run 2: timing run (~8 minutes)
```

Run 1 answers "does this `train_steps` reach the target?"; run 2 answers "how many seconds is a step over the 200 Mb/s link?"; `T = train_steps × s/step`. Always redirect as above — never tee or let a run's output into your context.

**Optional speedup: a DDP twin for the loss run.** Run 1 is mostly pipeline bubble; a data-parallel `train_gpt_ddp.py` does the same run in ~25 minutes (~0.2 s/step). It is a valid run 1 only if its convergence matches the pipeline:
- Same model, optimizer, schedule and `train_steps`, copied verbatim; gradients summed across ranks. Whatever `train_gpt.py` does to a tensor at a stage boundary, the twin does in-process at the same point, forward and backward.
- Validate before trusting it and after every model edit (edits go into both files). ~250 steps of both scripts (`WAN_MODE=off`), val at 125 and 250; ~0.01 apart is init noise, a growing gap is divergence.
- Once validated, its loss run *is* the measurement — don't also run `WAN_MODE=off train_gpt.py` to confirm a keep. That is the human's job at submission. The twin itself is never submitted.

**Optional speedup: early kill.** A run that is clearly behind the baseline at step 1000–2000 won't recover. Kill it and log it as `discard`, noting the step in the description. Changes whose effect only shows in the anneal must run to the end.

**Optional speedup: the stat-sig stop scan.** Don't spend one full run per `train_steps` trim (5900 → 5800 → 5700…). Run one horizon; the script already prints val every 25 steps near the end. The earliest step whose val is ≤ 3.276 is a valid stop under README Rule 5 (the stopping criterion is fixed, not picked per run): quote `T = that step × s/step` and log that step in the `train_steps` column. Fold the trim into the *next* keep by setting its `train_steps` near the quoted stop — a shorter horizon anneals earlier and usually crosses lower. If no step reaches 3.276, it's a discard as usual.

**What you can change:** anything in `train_gpt.py` — architecture, wire codec, optimizer, hyperparameters, `train_steps`, training loop, `mbs`, pipeline schedule.

**The goal is simple: get the lowest T.** Each idea gets one run, so README Rule 3 applies at n=1: **the loss run must finish below 3.276, not 3.28.** The scripts' `TARGET 3.276 REACHED` line tests the same 3.276 — read the `val_loss` number for the margin. A near-miss (3.276–3.28) is a discard. Do not rerun it hoping for a better init.

**Simplicity:** all else equal, simpler is better. A small gain that adds hacky complexity is not worth it; equal or better results from deleting code is a keep.

## Reading results

Rank 0 writes `logs/<uuid>.txt` (the path is the first line the script prints): the full `train_gpt.py` source followed by every val line — exactly what a record directory needs.

```
grep "^TARGET" run1.log            # final val_loss
grep "^T = " run2.log              # the score, for the train_steps set in train_gpt.py
grep "^STEADY" logs/<uuid>.txt     # steady step_avg (log file only, not console)
```

The timing run stops itself once three 10-step val windows agree within 1% (typically step 40, ~8 minutes). A miss on run 1 is a discard, not a crash: the loss is still worth recording.

## Logging results

Append to `results.tsv` (tab-separated, header row, 7 columns). Leave it untracked; do not commit it.

```
commit	val_loss	train_steps	step_s	T	status	description
50ca11a	3.27590	7500	7.8446	58834.5	keep	baseline k160 int8
9a1b2c3	3.27310	7200	7.8446	56481.1	keep	train_steps 7200 still clears 3.276
c3d4e5f	3.28410	7000	0.0000	0.0	discard	train_steps 7000 misses
7f8e9d0	3.28120	7500	4.1210	0.0	discard	int4 codes: cheap wire but misses 3.276 at 7500
d4e5f6g	0.00000	7500	0.0000	0.0	crash	SSN_K 250 (odd container width, packer assert)
```

`step_s` and `T` come from the `T = ` line; use 0.00000 / 0.0000 / 0.0 when there was no result. T is only a score if val_loss is below 3.276.

## The experiment loop

LOOP FOREVER:

1. Look at the git state (branch/commit). The very first experiment is the unmodified baseline.
2. Edit `train_gpt.py` (and `train_gpt_ddp.py` in lockstep, if you use one) with one idea by directly hacking the code; commit.
3. Run the loss run. Then, if it finished below 3.276 — or whenever the bytes on the wire changed (codec, `SSN_K`, `mbs`, schedule) — run the timing run. Optimizer, LR and init changes don't move s/step: reuse the last timing run.
4. `grep "^TARGET" run1.log; grep "^T = " run2.log`. No `TARGET` line means a crash: read the traceback; fix it if it's dumb (typo, import, memory knob), skip the idea if it's fundamentally broken and log `crash`. Give up after a few attempts.
5. Log the row.
6. Below 3.276 **and** T lower → keep the commit (advance the branch). Otherwise → `git reset` back to where you started.

**Timeouts:** loss run ~80 minutes on the pipeline (~25 with a DDP twin), timing run ~8. Kill a loss run past 2 hours (60 minutes for DDP) or a timing run past 15 minutes and treat it as a failure. Rewinding past a kept commit is allowed but should be very rare.

**NEVER STOP.** Once the loop has begun, do not pause to ask whether to continue or whether this is a good stopping point. The human may be asleep and expects you to keep working until manually stopped. If you run out of ideas, think harder: read the papers referenced in the code, re-read the in-scope files for new angles, combine previous near-misses, try more radical architectural changes.
