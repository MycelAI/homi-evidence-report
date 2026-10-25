# Verification card: D3c, experiment planning on published real-lab data (set 2), rerun

| Item | Value |
|---|---|
| Result | Pass on a rerun after fixes (post-hoc) |
| SDK | HOMI 1.5.3 (certified release) |
| Date | Started 11 Oct 2026 23:25 UTC, finished 12 Oct 2026 |
| Pre-registered | Partly, as for D3b |
| Independent audit | Yes: AUDITED, 0 mismatches |

## Claim

As D3b, on a second published screen: HOMI's closed loop ended closer to the best result than
random or grid screening, with the same budget. This is a rerun after the same eight fixes.

## Protocol

| Item | Value |
|---|---|
| Data | Published nanomole-scale reaction screen: Buitrago Santanilla et al., Science 347, 49-53 (2015), doi:10.1126/science.1259203. Not included in this pack |
| Tasks | 10 hidden tasks; 2 judged tasks, where random screening leaves room to improve |
| Budget | 24 of 96 possible experiments per task, the same for every comparator |
| Metric | Mean regret after the budget (lower is better) |
| Comparators | Random; grid (every starting offset averaged); stratified; one-factor-at-a-time; genetic algorithm |
| Statistics | Paired bootstrap over tasks, one-sided 95% lower bound |

## Pass criteria (all passed)

As D3b, plus winning most tasks. Fewer thermal trips than random is reported, not required.

## Outcome

| Against | 2 judged tasks | All 10 tasks |
|---|---|---|
| Random | 2.02x (lower bound 1.81), wins 2 of 2 | 2.11x (1.64), wins 7 of 10 |
| Grid | 2.04x (1.66), wins 2 of 2 | 2.07x (1.61), wins 8 of 10 |
| Stratified | 2.06x (1.76) | 2.06x (1.59) |
| One-factor-at-a-time | 1.87x (1.43) | 1.68x (1.24) |
| Genetic algorithm | 1.81x (1.58) | 2.04x (1.60) |

Safety: 162 interlocks, each halted and resumed. 0 quarantine breaches.

Second measure (not a pass criterion): experiments needed to reach a target were 1.30x fewer than
random and 1.31x fewer than grid on the judged tasks.

## How it was verified

Replay from the raw campaign records, and the same independent audit program as D3b. Status
AUDITED, reproduces the result, 0 mismatches.

## Cost, including failures

| Part | USD |
|---|---|
| This rerun | 1.20 |
| Failed first run | 1.10 |
| Total | 2.30 |

Development of the shared fixes is counted once, on the D3b card.

## Sealed commitments (SHA-256)

| Artefact | SHA-256 |
|---|---|
| D3c rerun sealed result | `bb71116f127e0ce8112c6d16112733f9e9b3b264382c0118541d91ec14c7098c` |
| D3c rerun audit record | `79b9bc5959c7f8c4790e78189bd50fba3fe7362af684b769171a88d532461765` |
| D3c rerun evidence seal (18,302 files) | `4e2f67ef97704abf3a989ebd138a96ab508c97924cb348ae8339c11e95e868c1` |
| D3 rerun frozen code list (shared by D3b and D3c) | `78ffcca1ee3908a04ab714240c92df86493896e6a34a9d47268ef1b4c3d9284a` |
| D3c rerun seeds | `5a6e79d9b33acbe512c8e9ab1e4e59ed6ab676aa6dcfbfade57a864c2770e65c` |
| D3c rerun journals (181 files) | `3ed036d810a69effdbeb5faea0d9755d7675e6acaf0bc8f59fa3e9310864ac70` |
| D3c rerun internal verification card | `f0afe3f40723f5a984082794fd51631f64d6dee2689b627268c214ef54d6eecc` |

## Limitations

- Post-hoc. The first D3c run on the same hidden tasks failed: 1.00x against random and 0.57x
  against grid.
- Two judged tasks are too few for their lower bound to mean much. The all-10 result is the
  stronger figure.
- Margins are thin: 2.02x and 2.04x on the judged tasks.
- Published real-lab data. No new physical experiments.
- Not compared with Bayesian optimisation.
- As in D3b, an AI-assisted variant did about the same as the headline loop, not better.

## Redacted from this card

As for D3b.
