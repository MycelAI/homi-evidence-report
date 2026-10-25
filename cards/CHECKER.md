# Verification card: checker, release certification of SDK 1.5.3

| Item | Value |
|---|---|
| Result | Pass: SDK 1.5.3 certified |
| Checker | ArkBench, our in-house release checker. Built and run by Mycel UG. Not a third-party test |
| Run | Started 7 Oct 2026 17:51 UTC; release gate passed 8 Oct 2026 |
| Pre-registered | Yes: gates and limits fixed against a recorded baseline before the run |

## Claim

SDK 1.5.3 passed every release gate of the checker. In 1,200 injected faults it never reported a
failed task as a success and never repeated a side effect.

## Protocol

| Item | Value |
|---|---|
| Task | A fixed matrix of controlled and live agent tasks, including 1,200 injected faults |
| Fault rule | A fault counts as handled only with the expected status, a stable error class and no duplicate side effect |
| Comparators | A recorded baseline run of the checker; an open-source agent toolkit (OpenAI Agents SDK 0.22.3) on the same fault set |
| Live spend | USD 1.10 against a ceiling of USD 6.00 |

## Outcome

| Measure | HOMI 1.5.3 | Comparator toolkit |
|---|---|---|
| Release gates passed | 29 of 29 | not applicable |
| Injected faults handled correctly | 1,200 of 1,200 | 1,100 of 1,200 |
| False successes | 0 | 100 |
| Duplicate side effects | 0 | 0 |
| Additional safety controls passed | 8 of 8 | not applicable (no equivalent) |

The two were also checked for giving the same answers on 1,942 tasks that both completed: 0
differences.

The 8 additional safety controls, by category:

| Category | Controls |
|---|---|
| Isolation (network and private-address blocking) | 2 |
| Access control (tool binding, no reuse of a one-time permission) | 2 |
| Integrity (tamper rejection, record integrity, trust after restart) | 3 |
| Human approval (resume only after a named approval) | 1 |

## How it was verified

The checker writes a manifest, a regression-gate file and a verification file, each hashed. A
release-gate record binds these hashes to the hash of the release package that was tested. The
verification file reports status "verified" in full mode.

## Sealed commitments (SHA-256)

| Artefact | SHA-256 |
|---|---|
| Checker run manifest | `851192415cdec938c3f8820159654489652214ca55afa04ad6eb677837bef750` |
| Checker regression gate (29 gates) | `14ed101f0b2056e200a8fd9915ec51812085f62e98da8ce935a3093d74b88d5d` |
| Checker verification record | `96a8e5f3b5772f01fd44e53398025038bb2bfe57dc6f912bea1c1822dac665b7` |
| SDK 1.5.3 candidate manifest | `a29083f53311a4113e769bd02ac8db67213c6ee9e6fbc26a8161767b8c0bb76c` |
| SDK 1.5.3 candidate package | `9b301456a9b636604056aaa6e44bcc1855c11e705745ad598be3c655ec196fb7` |

## Limitations

- The checker is our own. It is not an independent or third-party benchmark.
- It measures runtime behaviour, not model intelligence.
- All 100 comparator false successes fall in one fault class.
- The comparator figures apply to that toolkit version on that date only.
- Speed and capacity results from the same run are outside the scope of this pack.

## Redacted from this card

The checker's implementation, task definitions, fault definitions, gate limits, the internal names
of the safety controls, model and provider names, and host details.
