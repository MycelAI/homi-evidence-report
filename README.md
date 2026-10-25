# HOMI evidence report: certified results and verification cards

Version 1.0.0, October 2026. Published by Mycel UG (haftungsbeschränkt).

HOMI is an autonomous research system built by Mycel UG. It plans experiments, runs them through
software tools, checks the results and records each step as sealed evidence.

This pack reports what HOMI achieved on its certified release, SDK 1.5.3, and how each result was
checked. It also lists what failed. It does not describe how HOMI's methods work.

## Results

| Result | Outcome | Date | How verified | Card |
|---|---|---|---|---|
| D0: 24-hour unattended research loop | Pass: 100 cycles, 100 machine-verified statements, 24.2 h, 0 human actions, 0 restarts | 9 Oct 2026 | Separate verifier re-ran 11 of 11 checks on the sealed evidence | [D0](cards/D0.md) |
| D1: blind rediscovery exam | Pass: 18 of 18 results verified (rate 1.0, bar 0.9), 3 of 3 campaigns | 8 Oct 2026 | Exam graded offline against hidden answers; re-grade identical | [D1](cards/D1.md) |
| D2: new method on a computable task | Pass: 38,807 bins vs 38,925 for the best of 74 published methods tested (0.303% fewer; bar 0.25%), on 400 hidden instances of a synthetic workload | 9 Oct 2026 | Exact scorer; novelty check against a fixed set; rebuilt by a different AI model family, exact on 400 of 400 | [D2](cards/D2.md) |
| D3a: experiment planning, simulated lab | Pass: 2.16x lower regret than random (lower bound 1.65), 2.69x than grid (1.88); 12 hidden tasks x 48 experiments | 11 Oct 2026 | Full replay from raw records | [D3a](cards/D3a.md) |
| D3b: experiment planning, published real-lab data (set 1) | Pass on a rerun after fixes: 2.90x vs random (1.84), 2.43x vs grid (1.67) on 8 judged tasks; 2.19x and 2.01x on all 19 | 12 Oct 2026 | Replay and an independent audit, 0 mismatches | [D3b](cards/D3b.md) |
| D3c: experiment planning, published real-lab data (set 2) | Pass on a rerun after fixes: 2.02x vs random (1.81), 2.04x vs grid (1.66) on 2 judged tasks; 2.11x and 2.07x on all 10 | 12 Oct 2026 | Replay and an independent audit, 0 mismatches | [D3c](cards/D3c.md) |
| Checker: release certification of SDK 1.5.3 | Pass: 29 of 29 release gates; 1,200 of 1,200 injected faults handled; 0 false successes; 0 duplicate effects; 8 of 8 safety controls | 8 Oct 2026 | Our own in-house checker (ArkBench); not a third-party test | [Checker](cards/CHECKER.md) |
| Pilot: development check of two engine components | Component 1 kept (regret 3.18 vs 4.05, lower bound +0.28); component 2 marked expired (3.18 vs 3.29, lower bound -0.36) | 23 Oct 2026 | Paired comparison, 288 pairs; development tasks only | [Pilot](cards/PILOT.md) |

The first D3b and D3c runs failed. The D3b and D3c passes above are reruns on the same hidden data
after eight fixes. They are not blind first tests. See [NEGATIVE_RESULTS.md](NEGATIVE_RESULTS.md).

More detail per result: [EVIDENCE_SUMMARY.md](EVIDENCE_SUMMARY.md).

## Limitations

- No physical experiments. D3a used a simulator. D3b and D3c used published real-lab data.
- The D2 workload is synthetic, and it was defined by us. The novelty check covers a fixed set of
  74 methods, not the whole literature.
- D3 was compared with random, grid, stratified, one-factor-at-a-time and genetic-algorithm
  screening only. It was not compared with Bayesian optimisation.
- The checker and every verifier were built and run by Mycel UG. No result here has been
  reproduced by an outside party yet.
- The sealed evidence is not public. This pack publishes SHA-256 hashes of it, so that evidence
  shown later can be matched to what was sealed.

Full list: [LIMITATIONS.md](LIMITATIONS.md).

## What is in this pack

| File | Content |
|---|---|
| `README.md` | This page |
| `EVIDENCE_SUMMARY.md` | Claim, protocol, outcome, verification and limits for each result |
| `cards/` | One redacted verification card per result |
| `NEGATIVE_RESULTS.md` | Every failed, halted or stopped run behind these results |
| `LIMITATIONS.md` | What has not been shown |
| `SHA256SUMS` | Hashes of every file in this pack, and of the sealed artefacts |
| `CITATION.cff`, `.zenodo.json` | Citation and archive metadata |
| `LICENSE` | CC BY 4.0 |
| `CHANGELOG.md` | Version history |

## Checking the hashes

To check the files in this pack:

```bash
sha256sum -c --ignore-missing SHA256SUMS
```

Lines whose path starts with `sealed/` are commitments to sealed artefacts that are not in this
pack. `--ignore-missing` skips them. They prove that the artefact existed, unchanged, no later than
the date this pack was published.

## How to cite

Mycel UG (haftungsbeschränkt), "HOMI evidence report: certified results and verification cards",
v1.0.0, Oct 2026.

Licence: CC BY 4.0. See [LICENSE](LICENSE).
