# 20260918_reparamssn_baseline — T = 181,487.1 s

The unoptimised ReparamSSN reference (`train_gpt_ssn.py`): every block output
projection and the embedding are reparametrized through a shared seed-derived
rank-160 subspace around a fixed embedding, so each stage boundary carries the
160 bf16 subspace coordinates plus the token ids instead of the dense 1024-wide
activation. `encode`/`decode` carry the projection; `pack`/`unpack` are the
identity codec, 322 B/token each way against the dense baseline's 2048. The
freed parameters go to FFN width (hidden 11292 at d1024; 203,822,240 total,
under the cap). 1F1B at mbs=16 (32 microbatches). Both runs used the pinned
Docker image from the repo's `Dockerfile` (torch 2.14.0+cu130, Python 3.12.14),
started with the README's Docker commands.

Runs (n=1), 8xH100, real 8-stage pipeline:

- Run 1 (loss, `WAN_MODE=off`): `acdb22fd-….txt` — final val_loss **3.26424** at
  train_steps 9500 (< 3.276, the n=1 significance bar for 3.28).
- Run 2 (timing, `WAN_MODE=on`): `93db83fb-….txt` — steady **19.8890 s/step**,
  bytes_per_token 644.0. Full horizon: T = 9500 × 19.8890 s = 188,945.5 s.

Rule-5 claim (fixed stopping rule: earliest val ≤ 3.276 on the tail's 25-step
cadence): run 1 crosses at **step 9125** (val 3.27582), so
**T = 9125 × 19.8890 s = 181,487.1 s**.

`train_gpt_ssn.py` here is the exact file both runs executed (byte-identical to
the source embedded at the top of each log). `log.txt` is the two logs
concatenated, loss first, in the form submitted to the leaderboard.
