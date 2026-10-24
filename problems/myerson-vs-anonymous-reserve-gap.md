# The revenue cost of one reserve for everyone

**Open problem.** When bidders have different value distributions, how much revenue can an optimal auction gain over a second-price auction using one shared reserve? For independent regular bidders, construct an instance with certified OPT/AR ≥ 2.1600, where AR is optimized over every anonymous reserve.

**Status.** Jin, Lu, Tang and Xiao’s Theorem 3 reports a four-buyer ratio of about 2.1596. Their four-buyer calculation is numerical and the parameters are printed to limited precision, so a close comparison needs an independently certified value. Feng and Jin’s cited paper describes the remaining regular-bidder comparison as open. [Status source](<https://arxiv.org/abs/2411.03583>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

OPT denotes Myerson’s optimal expected revenue. AR denotes the best expected revenue from a second-price auction with the same reserve for every bidder. Regularity means that each bidder’s revenue curve, expected revenue as a function of sale probability, is concave under the source’s convention for atoms. Proposed distributions outside the triangular family require a proof of regularity. For finite triangular parameters, F(p)=(1−q)p/((1−q)p+vq) for 0 ≤ p < v, with an atom at v. This gives a concrete family in which bidder asymmetry can be varied. For illustration, Tri(1,1/2) has F(p)=p/(p+1) below 1 and an atom of probability 1/2 at 1.

## Backstory

- 2009: Hartline and Roughgarden conjectured a worst-case ratio of 2.
- 2019: Jin and coauthors refuted it with a three-buyer construction and reported the larger four-buyer example.
- November 2024: Feng and Jin restated the unresolved regular-bidder comparison.

## Why it matters

One common reserve is simpler to set and explain, but cannot respond separately to different bidder distributions. The ratio measures the largest revenue cost of that restriction in this model.

## Real-world uses

Certified examples can benchmark reserve optimization and demonstrate when distribution-specific auction design has a measurable advantage over a uniform reserve.

## How to think about it

A candidate must beat the best reserve, not an arbitrarily chosen one. Triangular distributions help because the cited lemma reduces reserve optimization to specified candidate points. Adding bidders may increase optimal revenue while keeping those competing reserve revenues balanced.

## What counts as a solution

Give independent triangular distributions with rational parameters, allowing the cited unbounded limit distribution, or other closed-form distributions with regularity proofs. Certify a lower bound on OPT and an upper bound on AR over all reserves, with their ratio at least 2.1600. Use exact formulas or rigorous interval integration, including justified tail bounds when needed. Apply the finite candidate-reserve lemma only where its hypotheses hold. Reproduce the published examples and compare later records before claiming.

The 2.1600 bar separates the claim from a rounded numerical incumbent. Match printed calibration values within one unit of the last printed digit.

## Our approach

Optimize rational triangular-bidder families with additional buyers. Independently certify optimal-auction revenue and every relevant reserve revenue, including any unbounded tails.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/pdf/1804.00480>
- <https://arxiv.org/pdf/2411.03583>
- Status source: <https://arxiv.org/abs/2411.03583>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
