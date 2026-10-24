# Can smaller tournament sets support unfair dice games?

**Open problem.** Can the open small tournament composition bounds be improved?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2604.08790>).

## The problem

Construct two tournaments on at most thirteen vertices that dominate every five-subset, or three tournaments on at most twelve vertices that dominate every six-subset. One vertex outside a subset must point to every member in a single tournament.

## Backstory

Joel Jeffries’s April 2026 paper defines this extension of Schütte’s property. Figure 7 gives composition bounds f(2,5)<=14 and f(3,6)<=13. It marks f(2,4)=10 as exact, so the input’s proposed improvement of that cell has been removed.

## Why it matters

The question tests how much a set of directed comparisons can compress a universal domination property. Smaller constructions would improve the paper’s published bounds.

## Real-world uses

The paper motivates the definition through dice with multiple roll modes and also mentions multi-issue voting and network monitoring. Producing tournaments alone does not produce physical dice.

## How to think about it

Published objects can be composed: add their orders and tournament counts, and add their subset parameters plus one. Two order-7 S2 objects give the bar 14. Two order-3 S1 objects and one order-7 S2 object give 13. Search must beat the best published composition, including later ingredients.

## What counts as a solution

Give adjacency matrices with exact domination checks over all subsets and an order below the applicable composition bar. State whether the object is composed and cite its ingredients. Integer orders need no numerical margin. Optimality is a separate question.

## Our approach and status

Use SAT or local repair on the two retained cells, then verify the final matrices directly and update the composition bar from published constructions. No smaller construction is claimed.

## Sources

- <https://arxiv.org/pdf/2604.08790>
