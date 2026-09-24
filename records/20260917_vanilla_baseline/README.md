# 20260917_vanilla_baseline — T = 293,889.4 s

The unmodified dense 8-stage pipeline baseline: bf16 boundary activations,
2048 B/token each way (4096 round trip), 1F1B at mbs=8 (64 microbatches). Both runs used the
pinned Docker image from the repo's `Dockerfile` (torch 2.14.0+cu130, Python
3.12.14), started with the README's Docker commands.

Runs (n=1), 8xH100, real 8-stage pipeline:

- Run 1 (loss, `WAN_MODE=off`): `04b78cf1-….txt` — final val_loss **3.27011** at
  train_steps 3000 (< 3.276, the n=1 significance bar for 3.28).
- Run 2 (timing, `WAN_MODE=on`): `aa699a1a-….txt` — steady **100.4750 s/step**,
  bytes_per_token 4096.0. Full horizon: T = 3000 × 100.4750 s = 301,425.0 s.

Rule-5 claim (fixed stopping rule: earliest val ≤ 3.276 on the tail's 25-step
cadence): run 1 crosses at **step 2925** (val 3.27443), so
**T = 2925 × 100.4750 s = 293,889.4 s**.

`train_gpt.py` here is the exact file both runs executed (byte-identical to the
source embedded at the top of each log). `log.txt` is the two logs
concatenated, loss first, in the form submitted to the leaderboard.
