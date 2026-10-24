# Can lottery menus outperform item prices by more?

**Open problem.** A buyer wants at most one item, but may be willing to buy a lottery over items. For independent item values, find a finite lottery menu with revenue R and a certified upper bound D on all deterministic item pricing such that R/D > 1 + ln(2)/5.

**Status.** Jin and Lu’s cited paper gives the gap as [1+ln(2)/5, 3], crediting the lower bound to Chawla, Malec and Sivan. The original paper’s appendix reports a rounded lottery-revenue calculation; a close comparison requires an independently checked calculation. [Status source](<https://arxiv.org/abs/2606.10169>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

A menu entry has allocation probabilities x_i ≥ 0 with ∑x_i ≤ 1 and price ℓ. A buyer with values v_i gets expected utility ∑x_i v_i−ℓ. For example, probabilities (1/2,1/2) offer one of two items at random. Deterministic item pricing offers each item at its own fixed price. The joint value distribution must be the product of the item distributions; correlation is outside this target.

## Backstory

- 2010: Chawla, Malec and Sivan gave the cited three-entry menu for two independent capped equal-revenue items.
- June 2026: Jin and Lu improved the general upper bound to 3 while restating the old lower bound.

## Why it matters

Random allocation can separate buyers who value the items differently, creating pricing options that fixed item prices cannot express. The question quantifies that advantage while keeping values independent.

## Real-world uses

Explicit menus can test mechanism-design solvers and compare randomized sales offers with deterministic prices. The result concerns expected revenue in a stated value model, not every customer population.

## How to think about it

A richer menu may extract revenue from buyers who are nearly indifferent between items, but can also divert buyers from expensive options. The benchmark is the best item pricing. A convenient rigorous upper bound is D=∑_i max_p p Pr[v_i≥p], though a tighter certified bound may help.

## What counts as a solution

Provide independent finite rational distributions or closed-form distributions and a finite rational menu. Compute revenue exactly or by interval-certified integration. Among utility-maximizing entries use the lowest-priced one, and choose no purchase when best utility is nonpositive. Prove the stated ratio against a valid upper bound on optimal item revenue; any restricted price search must be proved sufficient. Calibrate against the source menu with an independently checked revenue calculation, and check later lower bounds before claiming. Approximate incentive compatibility or favorable seller tie-breaking is insufficient.

An exact rational or symbolic certificate of any strict improvement counts. Refine bounds on ln 2 until the comparison is proved. Floating-point certificates retain the 10^−4 margin and require rigorous error bounds.

## Our approach

Search richer menus on independent value grids, then extract explicit rational offers. Independently evaluate buyer choices with conservative ties and certify the item-pricing comparison.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/pdf/1002.3893>
- <https://arxiv.org/html/2606.10169>
- Status source: <https://arxiv.org/abs/2606.10169>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
