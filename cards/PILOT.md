# Verification card: pilot, development check of two engine components

| Item | Value |
|---|---|
| Result | Component 1 kept; component 2 marked expired, kept in the frozen engine with a written reason |
| Status | Development check. Not a certified result |
| Engine | The frozen SDK 1.5.3 D3b engine, run with an analysis script outside the certified SDK |
| Date | 23 Oct 2026 |
| Pre-registered | Decision rule fixed before the check |

## Claim

On development tasks, component 1 (the lab notebook) clearly lowers regret. Component 2 (a
confirmation rule) did not show a benefit.

## Protocol

| Item | Value |
|---|---|
| Tasks | The 9 sealed D3b development tasks. No hidden tasks |
| Replicates | 32 per task: 288 paired runs, with and without each component |
| Metric | Loop regret (lower is better) |
| Rule | Keep if the mean benefit is above 0 and its one-sided 95% paired-bootstrap lower bound is above 0; otherwise expired |
| History | An earlier 8-replicate rehearsal was too noisy to decide. Its 8 replicates are part of the 32 |
| Model calls | None |

## Outcome

| Component | With | Without | Benefit (lower bound) | Helps in | Verdict |
|---|---|---|---|---|---|
| Component 1 (lab notebook) | 3.180 | 4.051 | +0.870 (+0.277) | 122 of 288 pairs | Keep |
| Component 2 (a confirmation rule) | 3.180 | 3.289 | +0.109 (-0.356) | 85 of 288 pairs (hurts in 61) | Expired |

## What happened to the expired component

Component 2 was not removed. The certified D3b engine stays frozen so that later reproducibility
reruns use exactly the certified code. The decision and its reason are recorded in the review.

## Sealed commitments (SHA-256)

| Artefact | SHA-256 |
|---|---|
| Pilot data, component 1 | `b5ba04540c6cc367a1761315ae1395d3f155f0fb2aa129dd29e04965fe4b2725` |
| Pilot data, component 2 | `2f6e7c4c1c2bffdb9badf33591afc9e487ed6da6ead38cb3864032b94a9f1eca` |

## Limitations

- Development tasks only.
- Not a certified result.
- It says nothing about hidden tasks or physical experiments.

## Redacted from this card

What each component does and how; the engine's method and settings; the budget share used by
component 2; internal file and rule identifiers.
