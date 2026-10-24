# Can fair assignment lotteries always be coupled fairly?

**Open problem.** Is there an SD-EF assignment with no Dec-EF decomposition?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2609.35192>).

## The problem

A rational assignment matrix gives each agent a lottery over objects. It is fair under stochastic dominance. Must there be a lottery over complete assignments with those marginals in which no agent envies another with probability greater than one half?

## Backstory

Keyi Li, Yihao He and Quanyi Li’s September 2026 preprint states the general conjecture and establishes the four-agent case. It also covers five agents with repeated preference types and every five-agent probabilistic-serial output. It credits the earlier work of Kawase, Suksompong, Sumita and Yokoi.

## Why it matters

Marginal lotteries do not determine which pairs of objects agents receive together. A fair matrix can have an unfair implementation even if a better coupling might exist.

## Real-world uses

The model applies to lotteries for indivisible assignments such as rooms and time slots. Certificates can benchmark methods that implement fractional allocation rules.

## How to think about it

The smallest remaining case has five agents with five distinct rankings. Search matrices satisfying all stochastic-dominance prefix inequalities. A bad greedy decomposition does not suffice: every decomposition of the proposed matrix must fail.

## What counts as a solution

Supply strict preferences, a rational bistochastic matrix, and an exact LP dual or Farkas certificate that every decomposition has some pairwise envy probability above one half. Check every permutation column. Any exact strict gap suffices.

## Our approach and status

Search vertices of the SD-EF polytope, optimize decomposition LPs, then rationalize a candidate and verify the dual independently. No infeasible instance or new gap is claimed.

## Sources

- <https://arxiv.org/pdf/2609.35192>
- <https://doi.org/10.1016/j.mathsocsci.2026.102532>
