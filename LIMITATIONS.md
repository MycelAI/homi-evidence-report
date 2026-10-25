# Limitations: what has not been shown

## Scope of this pack

- Only results on HOMI SDK 1.5.3, plus one development pilot on its frozen engine.
- Later SDK versions, speed and capacity measurements, and planned studies are outside this pack.
  Nothing here should be read as a result for them.

## Physical world

- No physical or new real-lab experiments were run. D3a used a simulator. D3b and D3c used
  published real-lab data, looked up from published screens.

## Blind testing

- The D3b and D3c passes are reruns after eight fixes, on the same hidden tasks as their failed
  first runs. They are not blind tests.
- The judged-task rule in D3b and D3c was one of those fixes. The all-task figures are reported
  beside the judged figures and also pass.
- D1 passed on a fixed exam after earlier attempts failed or halted.
- D0's verdict needed the verifier to be re-run once, with the correct program version.

## Comparators

- D3 was compared with random, grid, stratified, one-factor-at-a-time and genetic-algorithm
  screening. It was not compared with Bayesian optimisation.
- D2 was compared with 74 published heuristics on a synthetic workload. The 74 are a fixed set,
  not the whole literature, and the workload is not a public benchmark.

## Size of effects

- D2's gain is 0.3% fewer bins.
- D3's gains are about 2x to 3x lower regret against the comparators listed. On a second measure,
  experiments needed to reach a target, the gains were smaller: 1.30x to 1.77x against random on
  the judged tasks. Do not read the regret ratios as savings in the number of experiments.
- D3c's judged set has only 2 tasks.

## Role of AI models

- D0 and D1 test that the system runs, checks itself and re-derives known results. They do not
  show discovery of new results.
- The D3 headline figures do not rely on an AI model's choices. In D3b and D3c, a variant in which
  an AI model took part in choosing experiments did about the same as the headline loop, not
  better. Nothing here shows that any model's chemistry knowledge helped.
- "No false claims" in D1 applies to those 18 questions only. It is not a general statement about
  model errors.

## Learning and re-planning

- Nothing here shows HOMI adapting its plans, or learning from failure, during real research. The
  fixes between the first and second D3 runs were made by people.

## Independence

- Every verifier, the audit program and the checker (ArkBench) were built and run by Mycel UG. The
  checker is not a third-party benchmark.
- No result has been reproduced outside Mycel UG.

## Openness

- The sealed evidence, the code and the methods are not published. This pack gives SHA-256 hashes
  only.
- A hash proves that an artefact existed, unchanged, no later than the date this pack was
  published. It does not prove the earlier run dates shown on the cards.
- The published datasets used in D3b and D3c are cited, not included.
