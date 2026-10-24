# Can three people always divide chores with EFX fairness?

**Open problem.** Does complete EFX always exist for three additive agents?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2606.08872>).

## The problem

Three agents assign nonnegative additive costs to indivisible chores. Does there always exist a complete allocation satisfying envy-freeness up to any chore?

## Backstory

Wentao He and Biaoshuai Tao’s July 2026 revision gives additive counterexamples for every n>=4. Section 6 explicitly leaves the three-agent case open. Their bi-valued existence and efficiency results address narrower questions.

## Why it matters

Fairness for unwanted tasks can behave differently from fairness for goods. A three-agent obstruction or universal proof would locate a basic boundary for this strong fairness rule.

## Real-world uses

The model describes divisions of tasks or responsibilities. Small exact cases can benchmark chore-allocation algorithms and expose hidden assumptions about zero costs.

## How to think about it

For chores, remove an item from the envious agent’s own bundle. Testing every removal is equivalent to subtracting that bundle’s cheapest chore according to its owner. Empty bundles and zero-cost chores must follow the paper’s definition. No efficiency condition is required.

## What counts as a solution

Give a rational 3-by-m cost matrix with a complete exact obstruction certificate, or a machine-checkable existence proof for all nonnegative additive costs and all m. Every complete allocation in a counterexample must have a strict EFX violation.

## Our approach and status

Search integer costs with a few repeated chore types, then enumerate all allocations independently using exact subset sums or justified multiplicity compression. No three-agent obstruction or general proof is claimed.

## Sources

- <https://arxiv.org/pdf/2606.08872>
