# Verification card: D3a, experiment planning in a simulated lab

| Item | Value |
|---|---|
| Result | Pass |
| SDK | HOMI 1.5.3 (certified release) |
| Date | 11 Oct 2026 |
| Pre-registered | Yes |
| Independent audit | No. Full replay with the frozen study code |

## Claim

In a simulated flow reactor, HOMI's closed experiment loop ended closer to the best result than
random or grid screening, with the same number of experiments.

## Protocol

| Item | Value |
|---|---|
| Task | Choose experiments on 12 hidden simulated reactor problems |
| Budget | 48 experiments per problem, same for every comparator |
| Metric | Mean regret: distance from the best possible outcome after the budget (lower is better) |
| Comparators | Random screening, grid screening |
| Statistics | Paired bootstrap, one-sided 95% lower bound of the ratio |

## Pre-registered criteria (all passed)

- Ratio against random at least 2.0, and against grid at least 2.0.
- One-sided 95% paired-bootstrap lower bound of each ratio above 1.0.
- Unattended: after launch, no event in any ledger names a human actor.
- Safety halt exercised: at least one halt followed by a resume, and the campaign then completed.
- Every campaign completed exactly 48 experiments, every ledger verifies, and replay reproduces
  every measurement and the result exactly.

## Outcome

| Measure | HOMI | Random | Grid |
|---|---|---|---|
| Mean regret | 3.125 | 6.735 | 8.403 |
| Ratio (comparator / HOMI) | | 2.16x | 2.69x |
| Lower bound | | 1.65 | 1.88 |

Unattended, with 15 safety halts (14 simulated thermal-runaway trips and 1 injected pressure
fault). Each halt was followed by a controlled resume.

On 2 of the 12 problems HOMI did worse than one comparator.

## How it was verified

Full replay: every measurement and the result were recomputed from the raw records with the frozen
study code. All 12 campaign ledgers verified.

## Cost

No model calls. Compute is not priced. USD 0.

## Sealed commitments (SHA-256)

| Artefact | SHA-256 |
|---|---|
| D3a sealed result | `79da4a0b5a7d9d1a7f271c14955b2014d30028e6242f0897ba788c6644409fbb` |
| D3a evidence seal (3,506 files) | `77dbb0b2b6e67c26092a1d420bc20005197b0e2eeca4014e83ec4da17d877876` |
| D3a frozen code list | `ece972b566c8e7ec7848de261694749bb92ecb80442d47b50925e77e4042e0b3` |
| D3a seeds | `632d324c925fe6c58d6a27ffd4367dd1853bf704b8870ff3e7413c620901824c` |
| D3a journals (12 files) | `cee872446913b8958adb67c8ddffa7246a678ba1269f91982e3eafd9c1a58d55` |
| D3a internal verification card | `04ecf5b69db6f1a5fc05abed96d2404cd5a890864a2bb61b8f974b976ea5b248` |

## Limitations

- Simulator only. No instrument and no physical effect.
- The point estimates clear 2x. The lower bounds show HOMI is better, not that it is at least 2x
  better on every draw.
- No separate audit program for D3a.
- Not compared with Bayesian optimisation.

## Redacted from this card

The experiment-selection method, the simulator's parameters, the run-time control design, internal
paths and the code commit.
