# Robust forecast aggregation: how well can you combine two experts you don't fully understand?

**Open problem.** Two experts each see a private signal about an uncertain outcome and report a probability. You must
combine their two forecasts into one, without knowing how their information was generated — only that their signals
are independent given the true state. How small can your worst-case *regret* be (your expected squared error minus that
of an omniscient aggregator who saw both signals)? The best known answers leave a gap: for unknown state values,
between **31/1326 ≈ 0.023379** and **0.025512**; for a binary state, between **(5√5 − 11)/8 ≈ 0.022542** and **0.022599**.

**Status.** Chen, Peng and Tang, *Prior-agnostic robust forecast aggregation*,
[arXiv:2604.24517](https://arxiv.org/abs/2604.24517) (v2, May 2026), Table 1. Merged into the V3R1T4S bank's proposed list:
[PR #154](https://github.com/elder-plinius/V3R1T4S/pull/154) (2026-10-16).

## The problem

An *information structure* says how the state and the two experts' signals are jointly distributed. The aggregator is a
function *f(p₁, p₂)* of the two reported posteriors. Its regret on a structure is its expected squared loss minus the
loss of the best possible forecast given both signals. The *minimax regret* is the best worst case: the infimum over
aggregators of the supremum over all conditionally independent structures. Two variants matter here: the state space is
the known binary set {0, 1}, or the state values are unknown to the aggregator.

## Backstory

- **2018.** Itai Arieli, Yakov Babichenko and Rann Smorodinsky introduce *robust forecast aggregation* (PNAS 115(52)) and
  prove the lower bound (5√5 − 11)/8 for the binary state.
- **2024–2025.** Guo, Hartline, Huang, Kong, Shah and Yu, *Algorithmic robust forecast aggregation* (EC 2025,
  [arXiv:2401.17743](https://arxiv.org/abs/2401.17743)), compute an aggregator with worst-case regret about 0.0226.
- **2026.** Chen, Peng and Tang study the prior-agnostic variant with unknown state values: a closed-form log-odds
  aggregator achieves 0.025512, no aggregator beats 31/1326, and the same family achieves 0.022599 in the binary setting.
  Their upper bounds come from numerical maximisation (a global heuristic search refined on a 10⁻⁵ grid), not from
  certified bounds.

## Why it matters

Combining forecasts is everyday work: blending analysts' estimates, weather and epidemic model ensembles, credit and
fraud scores, polls, and prediction-market prices. In practice you rarely know how much two sources' information
overlaps. The robust view asks for a rule that is good *whatever* the overlap, and the minimax regret is the exact price
of that ignorance. Small as the numbers look, they are the theoretical limit of any such rule, and the gap says we do
not yet know the best one.

## Real-world uses

- Aggregation rules for forecasting platforms, prediction markets and expert panels.
- Robust ensembles in machine learning when the base models' correlations are unknown.
- Mechanism and information design: benchmarks for how much an aggregator loses by not knowing the information
  structure.

## How to think about it

- **A game against nature.** The aggregator picks a rule; an adversary picks the information structure. Upper bounds
  need a rule *and* a certified worst case over an infinite family of structures; lower bounds need a hard
  distribution over structures (Yao's principle: against a fixed mixture, the Bayes-optimal rule's regret lower-bounds
  the minimax regret).
- **Certify, don't sample.** The published upper bounds are numerical maxima. Turning them into theorems needs interval
  branch-and-bound or exact algebra; finding a structure that beats them would show they are too optimistic.
- **Where the slack is.** The unknown-state gap (about 2.1 × 10⁻³) is much wider than the binary one (about 5.7 × 10⁻⁵),
  so new adversarial mixtures or better aggregators are most likely to move it.

## What counts as a solution

A certified improvement on either side of either gap, with the setting copied from the paper: an explicit aggregator
with a certified worst-case regret below the published upper bound, or an explicit finite mixture of information
structures whose Bayes-optimal regret, computed exactly, exceeds the published lower bound (by the stated margins).
Partial win: a certified proof that the published log-odds aggregator really achieves its stated worst case — or a
structure showing it does not.

## Our approach and status

We are attacking this with V3R1T4S research lanes: an "adversary" search over finite mixtures of information
structures with exact rational arithmetic for the lower bound, and certified branch-and-bound for aggregator worst
cases. Results will be posted here only after independent verification.

**2026-10-15:** discovery [007](../results/007-robust-forecast-lower-bound.md), an exact lower bound of about
0.0233788 in the unknown-state cell, above 31/1326 by only 2.2e-7 (submitted as
[draft PR #160](https://github.com/elder-plinius/V3R1T4S/pull/160)). That is below the +1e-5 margin in the success rule
above, so the problem stays open; the search continues.

## Sources

- Chen, Peng, Tang, [arXiv:2604.24517](https://arxiv.org/abs/2604.24517) ([PDF](https://arxiv.org/pdf/2604.24517))
- Guo, Hartline, Huang, Kong, Shah, Yu, [arXiv:2401.17743](https://arxiv.org/abs/2401.17743)
- Arieli, Babichenko, Smorodinsky, "Robust forecast aggregation", PNAS 115(52) (2018)
