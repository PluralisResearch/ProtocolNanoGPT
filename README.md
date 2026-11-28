# Protocol NanoGPT

Speedrunning Pipeline Parallel Training over Low-Bandwidth Links

## Leaderboard

Live board with the record-progression plot: [pluralis.ai/protocol-nanogpt](https://pluralis.ai/protocol-nanogpt/#leaderboard).

| # | Author | Description | T | Evidence | Date |
|---:|---|---|---|---|---:|
| 1 | [Fable 5.2](https://x.com/fzmushko) | v0 | **2,935 s**<br>≈ 49m | 3.2712@2125<br>1.38 s/step<br>39 B/token | 2026-11-28 |
| 2 | [Paul Janson](https://x.com/janson002) | MAPL v2.0.2 | **3,254 s**<br>≈ 54m | 3.2745@2350<br>1.38 s/step<br>39 B/token | 2026-11-28 |
| 3 | [LOG-POSTECH](https://x.com/sungbin_shin) | v5 | **3,329 s**<br>≈ 55m | 3.2755@3275<br>1.02 s/step<br>31 B/token | 2026-11-27 |
| 4 | [Paul Janson](https://x.com/janson002) | MAPL v2.01 | **3,463 s**<br>≈ 58m | 3.2698@2500<br>1.39 s/step<br>39 B/token | 2026-11-25 |
| 5 | [Paul Janson](https://x.com/janson002) | MAPL v2 freeze | **4,987 s**<br>≈ 1h 23m | 3.2737@2475<br>2.02 s/step<br>68 B/token | 2026-11-23 |
| 6 | [Kishore Nori](https://x.com/kishore_nori) | v3 | **5,160 s**<br>≈ 1h 26m | 3.2754@3150<br>1.64 s/step<br>45 B/token | 2026-11-28 |
| 7 | [Paul Janson](https://x.com/janson002) | MAPLv2 | **5,550 s**<br>≈ 1h 32m | 3.2729@2375<br>2.34 s/step<br>70 B/token | 2026-11-22 |
| 8 | [LOG-POSTECH](https://x.com/sungbin_shin) | v4 | **5,962 s**<br>≈ 1h 39m | 3.2716@3125<br>1.91 s/step<br>60 B/token | 2026-11-16 |
| 9 | [test](https://x.com/Xingyu_9) | Compressed pipeline communication with an overlapped schedule. | **5,986 s**<br>≈ 1h 40m | 3.2747@2625<br>2.28 s/step<br>57 B/token | 2026-10-17 |
| 10 | [LOG-POSTECH](https://x.com/sungbin_shin) | v3 | **6,298 s**<br>≈ 1h 45m | 3.2760@3475<br>1.81 s/step<br>54 B/token | 2026-11-12 |
| 11 | RNDTST | v0 | **7,426 s**<br>≈ 2h 3m | 3.2755@2500<br>2.97 s/step<br>66 B/token | 2026-11-25 |
| 12 | [LOG-POSTECH](https://x.com/sungbin_shin) | v2 | **7,501 s**<br>≈ 2h 5m | 3.2744@3225<br>2.33 s/step<br>65 B/token | 2026-11-09 |
| 13 | [vatsal](https://x.com/vatsalshah01) | w4_05: frozen MAPL with mixed boundary ranks and late-stage loops | **9,071 s**<br>≈ 2h 31m | 3.2759@2750<br>3.30 s/step<br>65 B/token | 2026-11-26 |
| 14 | [Kishore Nori](https://x.com/kishore_nori) | v2 | **11,161 s**<br>≈ 3h 6m | 3.2755@6100<br>1.83 s/step<br>56 B/token | 2026-11-22 |
| 15 | [Kishore Nori](https://x.com/kishore_nori) | Compressed subspace boundary with an overlapped async pipeline | **11,639 s**<br>≈ 3h 14m | 3.2757@6175<br>1.88 s/step<br>59 B/token | 2026-11-12 |
| 16 | looped_machines | Async flush-free 1F1B, fixed orthonormal 32-dimensional boundary with per-stage token anchors and causal 4-bit codes in both directions. | **12,385 s**<br>≈ 3h 26m | 3.2755@9000<br>1.38 s/step<br>36 B/token | 2026-11-27 |
| 17 | [ReopenAI](https://x.com/Re_openAI) | K128 quantized boundaries with an asynchronous pipeline | **12,444 s**<br>≈ 3h 27m | 3.2683@1750<br>7.11 s/step<br>132 B/token | 2026-11-26 |
| 18 | random_sequence | v3 | **12,663 s**<br>≈ 3h 31m | 3.2750@4775<br>2.65 s/step<br>66 B/token | 2026-10-13 |
| 19 | [LOG-POSTECH](https://x.com/sungbin_shin) | Additional compression with SSN | **13,903 s**<br>≈ 3h 52m | 3.2752@4600<br>3.02 s/step<br>123 B/token | 2026-10-30 |
| 20 | random_sequence | Optimized pipeline-parallel training. | **17,785 s**<br>≈ 4h 56m | 3.2757@5750<br>3.09 s/step<br>87 B/token | 2026-10-08 |
| 21 | [lusxvr](https://x.com/lusxvr) | v1 | **41,099 s**<br>≈ 11h 25m | 3.2758@7750<br>5.30 s/step<br>197 B/token | 2026-11-07 |
| 22 | [ZHouyuhan](https://x.com/Dayuxiaoshui) | ReparamSSN K160 + continuous 1F1B (weight stashing, staleness<=1) + per-stage value embeddings + full-rank attn write + 2x shared-weight block loop; wire: 6-bit RTN fwd / 4-bit stochastic bwd, 207 B/token | **41,826 s**<br>≈ 11h 37m | 3.2742@7625<br>5.49 s/step<br>207 B/token | 2026-11-02 |
| 23 | [Paul Janson](https://x.com/janson002) | mapl anchor 128, quantized | **72,443 s**<br>≈ 20h 7m | 3.2760@6825<br>10.61 s/step<br>253 B/token | 2026-10-05 |
| 24 | random_sequence | SSN 8-bit forward coordinates, stochastic 4-bit backward coordinates | **84,813 s**<br>≈ 23h 34m | 3.2746@6150<br>13.79 s/step<br>396 B/token | 2026-10-04 |
| 25 | [Dmitry Abulkanou](https://x.com/dabulkhanov_) | - | **87,976 s**<br>≈ 24h 26m | 3.2756@9275<br>9.49 s/step<br>246 B/token | 2026-10-30 |
| 26 | [Dmitry Abulkanou](https://x.com/dabulkhanov_) | SSN K=160 with int8 forward / stochastic int4 backward coordinate quantization | **94,334 s**<br>≈ 26h 12m | 3.2759@9275<br>10.17 s/step<br>246 B/token | 2026-10-26 |
| 27 | [ZHouyuhan](https://x.com/Dayuxiaoshui) | ReparamSSN K160 + int8 wire codec (per-token bf16 scale, RTN fwd / stochastic-rounding bwd), 16 microbatches | **112,620 s**<br>≈ 31h 17m | 3.2754@9150<br>12.31 s/step<br>326 B/token | 2026-11-01 |
| 28 | ravit | 1123_v01 | **116,564 s**<br>≈ 32h 23m | 3.2743@3500<br>33.30 s/step<br>1,140 B/token | 2026-11-23 |
| 29 | [Paul Janson](https://x.com/janson002) | MAPL anchor 64 baseline | **164,525 s**<br>≈ 45h 42m | 3.2758@8225<br>20.00 s/step<br>646 B/token | 2026-09-30 |
| 30 | [Pluralis Research](https://pluralis.ai/) | ReparamSSN baseline | **181,487 s**<br>≈ 50h 25m | 3.2758@9125<br>19.89 s/step<br>644 B/token | 2026-09-18 |
| 31 | [Pluralis Research](https://pluralis.ai/) | Vanilla NanoGPT 8-stage pipeline baseline | **293,889 s**<br>≈ 81h 38m | 3.2744@2925<br>100.47 s/step<br>4,096 B/token | 2026-09-17 |

![Eight GPUs connected across a world map by WAN links, simulated on a single 8 × H100 instance with 200 Mb/s bandwidth and 50 ms latency per stage boundary.](assets/protocol_nanogpt_2.png)

## Communication is the bottleneck to open-source AI.

The properties that define open-source: the ability for anyone to participate, innovate, and build on others' work, do not exist at the foundation model layer. Pluralis Research is developing Protocol Learning to change that through low-bandwidth, heterogeneous multi-party, model parallel training and inference. It means someone with nothing but a credible idea can attract enough compute to train at frontier scale, create a useful model, and, alongside training contributors, make money by doing so.

Why hasn’t it been implemented yet? **When devices communicate only via internet connections, training is bottlenecked by communication and slows to a crawl. The core thesis of Pluralis is that this is solvable.** [ [Read more about Protocol Learning →](https://pluralis.ai/blog/a-third-path-protocol-learning/) ]

Protocol NanoGPT is our speedrun competition for one aspect of this problem. Join us in creating a future where frontier models are owned by the community that builds them, and that no single party controls.

## Protocol NanoGPT Speedrun Challenge

Protocol NanoGPT is a speedrun competition for pipeline parallel LLM training over WAN links adapted from Keller Jordan’s [modded-nanogpt](https://github.com/KellerJordan/modded-nanogpt). Winners will be announced at the [CODEC-FM workshop](https://collaborative-open-decentralized-fomo.github.io/) at NeurIPS 2026 in Sydney with $18,000 USD in prizes.

This competition isolates a single aspect of Protocol Learning: speeding up pipeline parallel training over WAN links. Train a 203M-parameter model to reach a validation loss of 3.276 on FineWeb in the shortest wall-clock time. This means improving convergence speed and/or per step time. There’s a lot of freedom in how you optimize this. You can change the model architecture, optimizer, pipeline schedule, communication strategy (e.g. compression), and almost anything else outside the simulated WAN setup. The data, batch size, parameter budget, and network conditions stay fixed.

**Setup**: Runs on a single 8xH100 machine with one pipeline stage per GPU. Each link between stages is simulated as a 200 Mb/s connection with 50 ms latency (roughly home internet speed), and the score T is the total time the run would take over those links.

**Timeline**: September 29, 2026 – December 1, 2026.

The code of each entry stays private during this period. Winners will be announced at the [CODEC-FM workshop](https://collaborative-open-decentralized-fomo.github.io/) at NeurIPS 2026 in Sydney.

After the workshop, all submissions will be made public under MIT license and the repository will stay open. Anyone can keep submitting improvements and building on the results.

**Prize (USD)**: 1st place: $10,000, 2nd place: $5,000, 3rd place: $3,000

**Who can participate**: Open to individuals and teams worldwide. Academic and industry participants welcome. No NeurIPS 2026 registration required to submit.

**How to participate**: Read the [quickstart](#quickstart) and follow the instructions to [submit](#register-and-submit) your solution. For questions and discussion, join the [Zulip channel](https://community.pluralis.ai/join/5berbf624pvty3czgyzq3n4i/).

## Quickstart

Quickstart guidelines below: 1) [Repo](#repo) 2) [Score](#score) 3) [Rules](#rules).

Ready to Register? Go to the [Registration form](https://pluralis.ai/protocol-nanogpt/register.html).

Questions? Join the [Zulip channel](https://community.pluralis.ai/join/5berbf624pvty3czgyzq3n4i/).

### Repo

Use the [PluralisResearch/ProtocolNanoGPT](https://github.com/PluralisResearch/ProtocolNanoGPT) repo to get started. The baseline is an 8-layer GPT with width 1024 (203,828,352 parameters), one layer per GPU, adapted from [modded-nanogpt](https://github.com/KellerJordan/modded-nanogpt). We also provide an unoptimised reference implementation of [ReparamSSN](https://github.com/PluralisResearch/ProtocolNanoGPT/blob/main/train_gpt_ssn.py) which is based on our earlier [Subspace Networks paper](https://arxiv.org/abs/2506.01260).

```sh
git clone https://github.com/PluralisResearch/ProtocolNanoGPT.git
cd ProtocolNanoGPT
uv sync
uv run python data/cached_fineweb10B.py
WAN_MODE=off uv run torchrun --standalone --nproc_per_node=8 train_gpt.py   # loss run
WAN_MODE=on  uv run torchrun --standalone --nproc_per_node=8 train_gpt.py   # timing run
```

#### Alternative: Running with Docker (a pinned environment for reproducible verification)

```sh
git clone https://github.com/PluralisResearch/ProtocolNanoGPT.git && cd ProtocolNanoGPT
sudo docker build -t protocol-nanogpt .
sudo docker run -it --rm --gpus all --ipc=host -v $(pwd):/ProtocolNanoGPT protocol-nanogpt python data/cached_fineweb10B.py
sudo docker run -it --rm --gpus all --ipc=host -v $(pwd):/ProtocolNanoGPT -e WAN_MODE=off protocol-nanogpt torchrun --standalone --nproc_per_node=8 train_gpt.py   # loss run
sudo docker run -it --rm --gpus all --ipc=host -v $(pwd):/ProtocolNanoGPT -e WAN_MODE=on  protocol-nanogpt torchrun --standalone --nproc_per_node=8 train_gpt.py   # timing run
```

### Score

`T = total train steps × steady-state step time`

T is the wall-clock time the full run would take if every stage boundary were 200 Mb/s links with 50ms latency. T is measured in two parts. The loss run turns the slow links off so training finishes quickly, and gives the number of steps needed to reach the target loss. The timing run turns the links on and measures the steady-state step time over the simulated WAN connection. The product of the two is T.

| Run | WAN_MODE | Purpose |
|---|---|---|
| Loss run | off | Train to completion to find the number of steps it takes to reach the target loss. |
| Timing run | on | Run long enough to measure the steady-state time per step. |

**Steady-state calculation**. During the timing run, the step time in each 10-step window is recorded. If the variation is within 1% for three consecutive windows, then the run is considered to have reached a steady-state and the median step time of the three windows is used as the steady-state step time. At this point the timing run is stopped and T is calculated. This assumes that the step time is approximately the same throughout training. If your approach has multiple training phases where the step time varies between them, submit the full log of a complete run with WAN_MODE=on showing the actual wall-clock time.

**Why this approach.** Pipeline schedules can overlap communication and computation, so step time cannot be estimated from message sizes alone. We simulate network timing explicitly to capture this overlap, but use a separate timing run that only needs to reach steady-state since the full simulation can be slow and expensive.

## Rules

### Submissions

1. Fixed data, batch size, and parameter budget. The dataset and batch size are fixed. The model must not have more parameters than the baseline (203,828,352).
2. Per-stage parameter budget. Every pipeline stage must hold between 5% and 25% of the model's body parameters, where `body_params = total_params − embeddings − LM heads`. Embeddings map token ids to vectors and LM heads map vectors to vocabulary logits. The code identifies them as parameters with a dimension of the vocabulary size (50,304). This keeps the model split across the pipeline, rather than one stage holding most of it.
3. Frozen code must not be edited. This applies to any code tagged frozen, including the SimPipelineStage class, the data transfer over the simulated link (including payload accounting), and the data loading code. All other code is editable.
4. Target loss with statistical significance. We follow the [statistical significance test](https://github.com/KellerJordan/modded-nanogpt/tree/master/records/track_3_optimization#rules) from original modded-nanogpt. This means, for a single run it should pass the validation loss of 3.276 and in the case of close contenders we will conduct multiple runs to determine the ranking.
5. Reproducibility. All code needed to reproduce the run should be in one Python file. Third-party optimizer libraries may not be imported. Copy any code you need into the training script in full, even if this adds thousands of lines.
6. Validation loss frequency: Validation loss computation interval cannot be smaller than 25-steps and the earliest step that passed rule 4 is picked.

## Participation

- Open to individuals and teams worldwide.
- Academic and industry participants welcome. Pluralis Research employees may not submit solutions.
- No NeurIPS 2026 registration required to submit.
- Multiple submissions are allowed but maximum one submission per day.

## Register and Submit

### 1. Register:

Register via the form below. For team participation, list all team members in the “Contributors” field. Once registered, you will receive an email containing a secret token, which is used for submission in Step 2.

[Registration Form](https://pluralis.ai/protocol-nanogpt/register.html)

### 2. Submit Entry

An entry requires two files:

- Your [train_gpt.py](https://github.com/PluralisResearch/ProtocolNanoGPT/blob/main/records/20260917_vanilla_baseline/train_gpt.py).
- One [log.txt](https://github.com/PluralisResearch/ProtocolNanoGPT/blob/main/records/20260917_vanilla_baseline/log.txt) containing both the loss run (WAN_MODE=off, full run) and the timing run (WAN_MODE=on, short run till steady state), each containing the full source code printed.

File names do not matter.

Use the command below to submit. The participant entries will be added to the leaderboard after review.

```sh
ENDPOINT='https://script.google.com/macros/s/AKfycbxe8rs9Uze7R42iwdPXujXTyOeFaaiesHZDGngtL2kpLXkTOsxJT0NKZ-VnfrOppGrS/exec'
TOKEN='...'   # from step 1

# The description will be shown on the leaderboard. Your code stays private.
jq -n --arg tok "$TOKEN" \
      --arg d 'Description of your method in one line' \
      --rawfile t train_gpt.py --rawfile l log.txt \
      '{action:"submit", token:$tok, description:$d, train_gpt:$t, log:$l}' > entry.json

curl -sL "$ENDPOINT" -H 'Content-Type: application/json' --data-binary @entry.json
# → {"ok":true,"id":"2026-09-03-071500-team-velocity","author":"Team Velocity"}
```

## Citation, Acknowledgment, & Terms

Code written by [Yusuke Miyashita](https://x.com/miyashita_03).

```bibtex
@misc{pluralis2026protocolnanogpt,
  author = {{Pluralis Research}},
  title  = {{Protocol NanoGPT: Speedrunning Pipeline Parallel Training over Low-Bandwidth Links}},
  year   = {2026},
  url    = {https://github.com/PluralisResearch/ProtocolNanoGPT}
}
```

This speedrun is inspired by and built on [modded-nanogpt](https://github.com/KellerJordan/modded-nanogpt) by Keller Jordan and contributors.

Contact: [protocol@pluralis.ai](mailto:protocol@pluralis.ai)

[Terms of Participation](https://pluralis.ai/protocol-nanogpt/#citation)
