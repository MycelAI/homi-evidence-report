# Negative results

This file lists every failed, halted or stopped run behind the results in this pack, as recorded
in HOMI's internal negative-results register. Entries are never removed or reworded after the
fact. A later pass does not change an earlier failure.

Some runs used earlier SDK versions. They are listed because they are part of the history of each
result. Costs are from each study's own ledger, not from invoices. "No confirmed charge" means a
cost was never confirmed. These count as 0 in the totals on the cards.

Terms:
- **Verified negative**: the run completed, its evidence verified, and it did not reach the bar.
- **Not achieved**: the run completed and missed at least one pass criterion.
- **Halted**: a safety or integrity check stopped the run.
- **Stopped**: the run was ended on purpose, by a rule or by the owner.

AI models are not named. Where it matters, they are labelled A to D. Each letter is one model,
used the same way throughout this file.

## D0: 24-hour unattended research loop

No D0 run failed. Two verdicts needed the verifier to be re-run:

| Date | What happened | Effect on the result |
|---|---|---|
| Aug 2026 (earlier SDK) | The verifier had a bug in the order in which it hashed files | Verifier fixed and re-run; pass confirmed. The run was not repeated |
| Oct 2026 (SDK 1.5.3) | The verifier was first run with the wrong program version | Re-run with the correct version; pass confirmed. The run was not repeated |

## D1: blind rediscovery exam

| Date | SDK | Outcome | Cause | Cost (USD) |
|---|---|---|---|---|
| 30 Aug 2026 | earlier | Halted, not graded | A network request timed out and, by design, was not retried | not available (one timed-out request) |
| 30 Aug 2026 | earlier | **Failed: 4 of 18 (22%)** | Below the 0.9 bar. Kept and not rescored | 0.011 |
| 30 Aug 2026 | earlier | Halted, not graded | The model provider returned a response status the system does not accept | 0.008, plus one call with no confirmed charge |

Verification incident on SDK 1.5.3: the re-grade wrote cache files into a sealed copy of the code.
The file-by-file check caught it. The files were removed and the match was proven again.

## D2: new method on a computable task

| Date | SDK | Model | Outcome | Cause | Cost (USD) |
|---|---|---|---|---|---|
| 30-31 Aug 2026 | earlier | not recorded here | **Verified negative** | Three finalists failed qualification: savings 0.059%, 0.062% and -0.124%, against the 0.25% bar | 24.51 |
| 2 Sep 2026 | 1.3.10 | not recorded here | Halted | Campaign safety halt | no confirmed charge |
| 2 Sep 2026 | 1.3.10 | not recorded here | Halted | A calibration step had an unresolved paid call | no confirmed charge |
| 2 Sep 2026 | 1.3.10 | not recorded here | Halted | Campaign safety halt | no confirmed charge |
| 2 Sep 2026 | 1.3.10 | B | Integrity halt | A launch prerequisite was not ready | 0 |
| 2 Sep 2026 | 1.3.10 | B | Integrity halt | Prerequisite evidence was lost | 0 |
| 4 Sep 2026 | earlier | B | Halted | Campaign safety halt | no confirmed charge |
| 4 Sep 2026 | earlier | B | Halted | Campaign safety halt | no confirmed charge |
| 4 Sep 2026 | earlier | B | Stopped | Owner stopped it after research cycle 162 | no confirmed charge |
| 4 Sep 2026 | earlier | not recorded here | Integrity halt | Test settings erased the run's history. A rebuilt history was not accepted | no confirmed charge |
| 4 Oct 2026 | 1.5.0 | not recorded here | **Verified negative** | All 3 finalists were new and beat 69 of 74 comparators, but missed the 0.25% bar against the 5 strongest | 6.62 |
| 4 Oct 2026 | 1.5.0 | not recorded here | Halted | A per-request resource limit ended a long model response | 0.67 |
| 4 Oct 2026 | 1.5.0 | not recorded here | Stopped | Two of three model calls hit the output length limit | 0.42 |
| 5 Oct 2026 | 1.5.0 | not recorded here | Stopped | Two unusable model responses in a row (a dropped connection, then a length limit) | 6.43 |
| 5 Oct 2026 | 1.5.0 | not recorded here | Stopped by owner | None given | 6.73 |
| 6 Oct 2026 | 1.5.1 | not recorded here | **Not achieved** | Finalist 1 beat all 74 comparators but failed review, because the review input lacked the workload sizes. A later amendment would pass it; the recorded verdict stays "not achieved" | 13.66 |
| 7 Oct 2026 | 1.5.1 | not recorded here | Stopped (pass only under a later amendment) | A campaign's 12-hour time limit ran out during a stall halt. One finalist qualified only under a later amendment, which does not count | 11.95 |
| 8 Oct 2026 | 1.5.3 | A | **Verified negative** | Weakest saving 0.120%, below 0.25%. Two finalists were identical | 14.31 |
| 8 Oct 2026 | 1.5.3 | C | Stopped | A connection defect after 17 calls | 0.63 |
| 8 Oct 2026 | 1.5.3 | C | **Verified negative** | Best finalist 0.218%, below 0.25%. Beat 73 of 74 | 1.13 |
| 8 Oct 2026 | 1.5.3 | C | Stopped by owner | No progress after 4 ideas. One rehearsal before it also failed, at no cost | 0.74 |
| 9 Oct 2026 | 1.5.3 | D | **Verified negative** | Finalists saved 0.113% to 0.131%, below 0.25% | 6.05 |

Total cost of these D2 runs: USD 93.85. With the passing study (USD 30.71): USD 124.57.

The passing D2 study on SDK 1.5.3 used model A. Its rebuild check used model B, from a different
model family.

## D3: experiment planning

| Date | Study | Outcome | Cause | Cost (USD) |
|---|---|---|---|---|
| 11 Oct 2026 | D3b first run, published screens set 1 | **Not achieved** | 1.44x against random and 1.16x against grid; 2x required | 2.51, plus about 5.00 development |
| 11 Oct 2026 | D3c first run, published screen set 2 | **Not achieved** | 1.00x against random and 0.57x against grid | 1.10 |

Both reruns that passed (see the D3b and D3c cards) ran after eight fixes, on the same hidden tasks.
The model spend of the development dry runs for those fixes was not recorded separately.

D3a (simulated lab) had no failed run.

## Pilot of 23 Oct 2026

| Item | Outcome |
|---|---|
| 8-replicate rehearsal | Too noisy to decide. Replaced by the 32-replicate check |
| Component 2 (a confirmation rule) | No benefit shown: lower bound -0.356. Marked expired; kept in the frozen engine with a written reason |

## Checker

| Run | Outcome | Cause |
|---|---|---|
| Checker for SDK 1.5.1, attempt 1 (6 Oct 2026) | Failed to start | Folder permissions in a new working copy. The retried run certified |
| Checker for SDK 1.5.1, certified run | Results lost | Deleted by a clean-up after a failed copy. The lesson: verify a copy before deleting |
| Checker for SDK 1.5.2 | Not run | Started by mistake against the owner's instruction. Stopped before any phase |
