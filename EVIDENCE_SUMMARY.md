# Evidence summary

All results below were produced on HOMI SDK 1.5.3, the release certified on 8 October 2026. The
pilot of 23 October 2026 is a development check. It ran on the frozen SDK 1.5.3 engine, using an
analysis script outside the certified SDK.

Each section gives the claim, the protocol, the outcome, how it was verified and its limits. The
cards in `cards/` give the sealed hashes and the costs.

"Pre-registered" means the pass criteria were written down and fixed before the scored run started.

---

## D0: 24-hour unattended research loop

**Claim.** HOMI ran a research loop for 24 hours with no human help after launch: 100 research
cycles, each ending in a statement that a separate verifier checked by machine.

**Protocol.**

| Item | Value |
|---|---|
| Task | Run research cycles over machine-checkable mathematical statements without human help |
| Metric | Cycles completed, statements verified, wall-clock time, human actions after launch |
| Comparators | None. This is a pass/fail endurance test |
| Budget | Spending cap of USD 1.00 for the whole run |
| Pre-registered | Yes. The 11 pass checks and the run profile were fixed before launch |

**Outcome.** Pass. Run from 8 Oct 2026 09:11 UTC to 9 Oct 2026 09:22 UTC. 100 cycles, 100
verified statements, 87,089 seconds (24.2 hours), 0 human actions, 0 restarts.

**Verification.** A separate verifier re-ran all 11 checks on the sealed evidence and passed all
11. The run's event ledger (1,404 events) verified end to end, and its final hash matched the
stored one.

**Limitations.**
- The statements were true and already known. D0 tests that the loop runs and checks itself. It
  does not test discovery.
- The first verdict file used the wrong program version for the verifier. The verifier was re-run
  with the right version and passed. The run itself was not repeated or changed.

---

## D1: blind rediscovery exam

**Claim.** In a sealed exam of 18 known mathematical results, hidden from HOMI, HOMI asserted 18
results and all 18 were verified correct.

**Protocol.**

| Item | Value |
|---|---|
| Task | Re-derive 18 hidden known results in three areas of mathematics, across three separate campaigns |
| Metric | Verification rate of asserted results; campaigns with verified results; distinct verified results |
| Comparators | None. Fixed bars: rate at least 0.9, at least 3 campaigns, at least 10 distinct results |
| Budget | Small model-call budget; total spend USD 0.019 |
| Pre-registered | Yes. The criteria were sealed with the exam |

**Outcome.** Pass on 8 Oct 2026. 18 of 18 verified (rate 1.0 against a bar of 0.9). 3 of 3
campaigns had verified results. 18 distinct results against a minimum of 10.

**Verification.**
- Grading ran offline, with no network, after every HOMI container had been removed.
- Two grading runs gave byte-identical verdicts.
- A scan of 40 output files found no leak of hidden answers.
- A later re-grade, with the clock set to the recorded grading time, matched the sealed verdict
  exactly.

**Limitations.**
- These are rediscoveries of known results, not new science.
- "No false claims" holds for these 18 questions only.
- Earlier attempts on 30 Aug 2026, on an earlier SDK, scored 4 of 18 or halted. The pass is on a
  fixed exam. It is not a first attempt.
- The re-grade once wrote cache files into a sealed copy of the code. This was caught, the files
  were removed, and the match was proven again.

---

## D2: new method on a computable task

**Claim.** HOMI produced a new heuristic for a synthetic online bin-packing workload. On 400
hidden test instances it used fewer bins than each of the 74 published heuristics tested.

**Protocol.**

| Item | Value |
|---|---|
| Task | Online bin packing on a synthetic workload defined by us |
| Metric | Total bins used on 400 hidden instances (fewer is better) |
| Comparators | 74 published heuristics, fixed before the study |
| Budget | Fixed model-call budget, tracked by a budget ledger; study spend USD 30.71 |
| Pre-registered | Yes. Pass required at least 0.25% fewer bins than the best comparator |

**Outcome.** Pass on 9 Oct 2026. 38,807 bins against 38,925 for the best comparator: 0.303% fewer.
Beat 74 of 74 comparators.

**Verification.**
- An exact scorer re-ran every candidate on the sealed instances and counted bins.
- A verify step re-checked the frozen code, the budget ledger, every model call against its raw
  record, each campaign ledger, the finalist selection and the qualification results.
- Re-running that verify step on a copy of the sealed evidence gave an identical result (about 8
  minutes).
- Novelty check against the fixed set of published heuristics and against every earlier D2
  candidate.
- Specification check and adversarial review.
- A different AI model family rebuilt the heuristic from its written specification alone. The
  rebuild gave exactly the same bin assignments on all 400 hidden instances, on the first of two
  allowed attempts.

**Limitations.**
- The workload is synthetic. It is not a public benchmark or customer data.
- The novelty check covers the 74 methods tested and earlier D2 candidates only.
- The gain is small: 0.3%.
- Three earlier D2 studies on SDK 1.5.3 missed the bar before this one passed. The full D2 series,
  including failures since August 2026, cost USD 124.57.
- Not reproduced outside Mycel UG.

---

## D3a: experiment planning in a simulated lab

**Claim.** In a simulated flow reactor, HOMI's closed experiment loop ended closer to the best
result than random or grid screening, with the same number of experiments.

**Protocol.**

| Item | Value |
|---|---|
| Task | Choose experiments on 12 hidden simulated reactor problems, 48 experiments each |
| Metric | Mean regret: distance from the best possible outcome after the budget (lower is better) |
| Comparators | Random screening, grid screening |
| Budget | 48 experiments per problem, same for every comparator |
| Pre-registered | Yes. Ratios of at least 2.0 against random and grid, lower bounds above 1.0, unattended, safety halt exercised, exact replay |

**Outcome.** Pass on 11 Oct 2026. Mean regret 3.125 for HOMI, 6.735 for random, 8.403 for grid.
Ratios 2.16x against random (one-sided 95% lower bound 1.65) and 2.69x against grid (1.88). Ran
unattended, with 15 safety halts (14 simulated thermal-runaway trips and 1 injected pressure
fault), each followed by a resume.

**Verification.** Full replay: every measurement and the result were recomputed from the raw
records with the frozen study code, and all 12 campaign ledgers verified. No independent audit.

**Limitations.**
- Simulator only. No instrument and no physical effect.
- The point estimates clear 2x. The lower bounds show HOMI is better, not that it is at least 2x
  better on every draw. On 2 of the 12 problems HOMI did worse than one comparator.
- Replay used the study's own code; there was no separate audit for D3a.

---

## D3b: experiment planning on published real-lab data (set 1)

**Claim.** On published reaction-screen data from real labs, HOMI's closed loop ended closer to the
best result than random or grid screening with the same budget. This is a rerun after fixes.

**Protocol.**

| Item | Value |
|---|---|
| Task | Choose experiments on 19 hidden tasks built from published reaction screens (Shields et al., 2021) |
| Metric | Mean regret after a fixed budget (lower is better) |
| Comparators | Random, grid (every starting offset averaged), stratified, one-factor-at-a-time, genetic algorithm |
| Budget | A fixed budget per task, the same for HOMI and every comparator |
| Pre-registered | Partly. The pass criteria were those of the first run. The judged-task rule and the budget rule were added after the first run failed |

Pass criteria: ratio at least 2x and lower bound at least 1.5 against random and against grid;
beat stratified, one-factor-at-a-time and genetic; fewer thermal trips than random; safety halts
exercised; AI agent in the loop; unattended; two forced-crash recovery drills; all campaigns
complete; replay; audit.

**Outcome.** Pass on 12 Oct 2026 (rerun).

| Against | 8 judged tasks | All 19 tasks |
|---|---|---|
| Random | 2.90x (lower bound 1.84) | 2.19x (1.63) |
| Grid | 2.43x (1.67) | 2.01x (1.57) |
| Stratified | 2.69x (1.87) | 2.06x (1.61) |
| One-factor-at-a-time | 2.20x (1.56) | 1.76x (1.38) |
| Genetic algorithm | 3.14x (1.94) | 2.29x (1.67) |

166 safety interlocks, each halted and resumed. 0 quarantine breaches.

**Verification.** Replay of every choice and measurement from the raw records. An independent
audit program, which imports no study code, recomputed every comparator, statistic and criterion
from the published data and the sealed records: status AUDITED, 0 mismatches.

**Limitations.**
- Post-hoc. The first D3b run on the same hidden tasks failed (1.44x random, 1.16x grid). Eight
  fixes were then made, and this rerun passed. It is weaker evidence than a blind first test.
- "Judged tasks" are those where random screening leaves room to improve. That rule was one of
  the fixes. The all-19 figures do not depend on it.
- Published data, not new physical experiments.
- On a second measure, experiments needed to reach a target, the gain was smaller: 1.77x against
  random and 1.69x against grid on the judged tasks.
- The audit program was written by Mycel UG.

---

## D3c: experiment planning on published real-lab data (set 2)

**Claim.** As D3b, on a second published screen. This is a rerun after the same fixes.

**Protocol.**

| Item | Value |
|---|---|
| Task | Choose experiments on 10 hidden tasks built from a published nanomole-scale reaction screen (Buitrago Santanilla et al., 2015) |
| Metric | Mean regret after a fixed budget (lower is better) |
| Comparators | Random, grid (every starting offset averaged), stratified, one-factor-at-a-time, genetic algorithm |
| Budget | 24 of 96 possible experiments per task, the same for every comparator |
| Pre-registered | Partly, as for D3b |

Pass criteria: as D3b, plus winning most tasks; fewer thermal trips is reported, not required.

**Outcome.** Pass on 12 Oct 2026 (rerun).

| Against | 2 judged tasks | All 10 tasks |
|---|---|---|
| Random | 2.02x (lower bound 1.81) | 2.11x (1.64) |
| Grid | 2.04x (1.66) | 2.07x (1.61) |
| Stratified | 2.06x (1.76) | 2.06x (1.59) |
| One-factor-at-a-time | 1.87x (1.43) | 1.68x (1.24) |
| Genetic algorithm | 1.81x (1.58) | 2.04x (1.60) |

162 safety interlocks, each halted and resumed. 0 quarantine breaches.

**Verification.** Replay, and the same independent audit program as D3b: status AUDITED, 0
mismatches.

**Limitations.**
- Post-hoc. The first D3c run failed (1.00x random, 0.57x grid).
- Two judged tasks are too few for their lower bound to mean much. The all-10 result is the
  stronger figure.
- Margins are thin: 2.02x and 2.04x on the judged tasks.
- On experiments needed to reach a target, the gain was 1.30x against random and 1.31x against
  grid on the judged tasks.

---

## Checker: release certification of SDK 1.5.3

**Claim.** SDK 1.5.3 passed every release gate of our in-house checker, ArkBench.

**Protocol.**

| Item | Value |
|---|---|
| Task | Run a fixed matrix of controlled and live agent tasks, including 1,200 injected faults |
| Metric | Release gates passed; faults handled with the expected status; false successes; duplicate side effects; safety controls |
| Comparators | A recorded baseline run; an open-source agent toolkit (OpenAI Agents SDK 0.22.3) on the same fault set |
| Budget | Live model spend USD 1.10 against a ceiling of USD 6.00 |
| Pre-registered | Yes. The gates and their limits were fixed against a recorded baseline before the run |

**Outcome.** Pass. Run started 7 Oct 2026 17:51 UTC; release gate passed 8 Oct 2026.

| Measure | HOMI 1.5.3 | Comparator toolkit |
|---|---|---|
| Release gates | 29 of 29 | not applicable |
| Injected faults handled correctly | 1,200 of 1,200 | 1,100 of 1,200 |
| False successes | 0 | 100 |
| Duplicate side effects | 0 | 0 |
| Additional safety controls | 8 of 8 | not applicable (no equivalent) |

**Verification.** The checker writes a manifest, a regression-gate file and a verification file,
each with a SHA-256 hash. A release-gate record binds those hashes to the hash of the exact
release package that was tested.

**Limitations.**
- The checker is our own. It is not a third-party test.
- It measures runtime behaviour, not model intelligence.
- All 100 comparator false successes fall in one fault class.
- The comparator result applies to that toolkit version on that date only.

---

## Pilot: development check of two engine components (23 Oct 2026)

**Claim.** A review of two components of the frozen D3b engine, on development tasks only: one
component helps clearly; the other did not show a benefit.

**Protocol.**

| Item | Value |
|---|---|
| Task | The 9 sealed D3b development tasks, 32 replicates each: 288 paired runs, with and without each component |
| Metric | Loop regret (lower is better) |
| Comparators | The same engine with the component switched off |
| Budget | No model calls |
| Pre-registered | The decision rule was fixed before the check: keep if the mean benefit is above 0 and its one-sided 95% lower bound is above 0. An earlier 8-replicate rehearsal was too noisy to decide; its 8 replicates are part of the 32 |

**Outcome.**

| Component | With | Without | Benefit (lower bound) | Helps in | Verdict |
|---|---|---|---|---|---|
| Component 1 (lab notebook) | 3.180 | 4.051 | +0.870 (+0.277) | 122 of 288 pairs | Keep |
| Component 2 (a confirmation rule) | 3.180 | 3.289 | +0.109 (-0.356) | 85 of 288 pairs | Expired |

Component 2 was marked expired but was not removed. It stays in the frozen engine, with a written
reason, so that the certified D3b engine is unchanged for later reproducibility reruns.

**Verification.** Paired comparison with a one-sided paired bootstrap. The data files are hashed in
`SHA256SUMS`.

**Limitations.**
- Development tasks only, not hidden tasks.
- Run with an analysis script outside the certified SDK. It is not a certified result.
- No AI model was involved in this check.
