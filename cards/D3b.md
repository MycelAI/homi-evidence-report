# Verification card: D3b, experiment planning on published real-lab data (set 1), rerun

| Item | Value |
|---|---|
| Result | Pass on a rerun after fixes (post-hoc) |
| SDK | HOMI 1.5.3 (certified release) |
| Date | Started 11 Oct 2026 23:42 UTC, finished 12 Oct 2026 |
| Pre-registered | Partly: pass criteria carried over from the first run; the judged-task rule and the budget rule were added after the first run failed |
| Independent audit | Yes: AUDITED, 0 mismatches |

## Claim

On published reaction-screen data from real labs, HOMI's closed loop ended closer to the best result
than random or grid screening, with the same budget. This is a rerun on the same hidden tasks after
eight fixes. It is not a blind first test.

## Protocol

| Item | Value |
|---|---|
| Data | Published reaction screens: Shields et al., Nature 590, 89-96 (2021), doi:10.1038/s41586-021-03213-y. Not included in this pack |
| Tasks | 19 hidden tasks; 8 judged tasks, where random screening leaves room to improve |
| Budget | Fixed per task, the same for HOMI and every comparator |
| Metric | Mean regret after the budget (lower is better) |
| Comparators | Random; grid (every starting offset averaged); stratified; one-factor-at-a-time; genetic algorithm |
| Statistics | Paired bootstrap over tasks, one-sided 95% lower bound |

## Pass criteria (all passed)

- Ratio at least 2x and lower bound at least 1.5, against random and against grid.
- Beats stratified, one-factor-at-a-time and genetic-algorithm screening.
- Fewer thermal trips than random.
- Safety-halt path exercised.
- AI agent in the loop.
- Unattended.
- Recovery: two forced-crash drills, each restarted without repeating an experiment.
- All campaigns complete; replay and audit pass.

## Outcome

| Against | 8 judged tasks | All 19 tasks |
|---|---|---|
| Random | 2.90x (lower bound 1.84), wins 8 of 8 | 2.19x (1.63), wins 18 of 19 |
| Grid | 2.43x (1.67), wins 8 of 8 | 2.01x (1.57), wins 18 of 19 |
| Stratified | 2.69x (1.87) | 2.06x (1.61) |
| One-factor-at-a-time | 2.20x (1.56) | 1.76x (1.38) |
| Genetic algorithm | 3.14x (1.94) | 2.29x (1.67) |

Safety: 166 interlocks, each halted and resumed. 0 quarantine breaches. 0.75 thermal trips per run
against 1.33 for random.

Second measure (not a pass criterion): experiments needed to reach a target were 1.77x fewer than
random and 1.69x fewer than grid on the judged tasks.

## How it was verified

1. Replay of every choice and measurement from the raw campaign records with the frozen study code.
2. An independent audit program, run in an isolated interpreter, imports no study code. It
   recomputed every comparator, statistic and criterion from the published data and the sealed
   records. Status AUDITED, reproduces the result, 0 mismatches.

## Cost, including failures

| Part | USD |
|---|---|
| This rerun | 3.10 |
| Development of the fixes | 5.00 |
| Failed first run | 2.51 |
| Total | 10.61 |

## The eight fixes, by category

| Category | Number of fixes |
|---|---|
| Method | 2 |
| Evaluation protocol | 3 (which tasks are judged; budget scaling; a budget floor) |
| Data handling (simulated measurement noise) | 1 |
| Comparator fairness | 1 |
| Reporting | 1 |

## Sealed commitments (SHA-256)

| Artefact | SHA-256 |
|---|---|
| D3b rerun sealed result | `5ce2b605ac77ca7e05c81f8f6d2109d81e49670272a7ea126d5d8c262869b019` |
| D3b rerun audit record | `0c204cdce0370d277755b23a7c6e9c416ad21614c26a36e3b389d5ee13bd0b58` |
| D3b rerun evidence seal (38,236 files) | `40b1051c3dab8595c904e937caea190c282345c0831a2a2f64a6dadf277d9bc9` |
| D3 rerun frozen code list (shared by D3b and D3c) | `78ffcca1ee3908a04ab714240c92df86493896e6a34a9d47268ef1b4c3d9284a` |
| D3b rerun seeds | `b21dbe93155848253f54921358f594d6be2fc482d6e37c3956fd3bf0705442e0` |
| D3b rerun journals (229 files) | `dd65167090e3800efbaf3d715c142834db1282a19cf3bfebd723a0a967f29a02` |
| D3b rerun internal verification card | `db4cb3f4f29bb064af3916e9502f9349a3d543a88e38fccd68eae0c66fb27739` |

## Limitations

- Post-hoc. The first D3b run on the same hidden tasks failed: 1.44x against random and 1.16x
  against grid. This rerun is weaker evidence than a blind first test.
- The judged-task rule was one of the fixes. The all-19 figures do not depend on it.
- Published real-lab data. No new physical experiments.
- Not compared with Bayesian optimisation.
- The headline loop does not rely on an AI model's choices. A variant in which an AI model took
  part in choosing experiments did about the same, not better. We make no claim that any model's
  chemistry knowledge helped.
- The audit program was written by Mycel UG.

## Redacted from this card

The content of the eight fixes, the experiment-selection method and its settings, the judged-task
threshold, the budgets per dataset, the simulated-noise settings, model names, internal paths, the
dataset copies used and the code commit.
