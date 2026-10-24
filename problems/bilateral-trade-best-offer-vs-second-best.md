# When both sides’ best offers trade too little

**Open problem.** A seller and buyer each know their own value but not the other’s. How inefficient can the better of their two profit-maximizing offer mechanisms be? Find independent finite rational value distributions and a feasible mechanism M with positive gains from trade such that max(GFT_SO,GFT_BO) < (3/4) GFT_M, with M itself no better than the second-best benchmark.

**Status.** Babaioff, Dobzinski and Kupfer’s 2021 paper gives the 3/4 example and explicitly contrasts it with the 1/2 guarantee credited to Brustle, Cai, Wu and Zhao. These are second-best gains-from-trade comparisons; the cited later first-best comparisons use a different benchmark. [Status source](<https://export.arxiv.org/api/query?search_query=abs:%22bilateral%20trade%22&sortBy=submittedDate&sortOrder=descending&max_results=50>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

If buyer value b exceeds seller value s, trading creates b−s in gains. First-best gains are E[(b−s)^+]. Second-best is the largest expected gain achievable with truthful reporting optimal in expectation, voluntary participation for every type in expectation, and no expected budget deficit. SO lets the seller choose a profit-maximizing price; BO lets the buyer do so. The better mechanism uses max(SO,BO), not their average. For an illustrative pair s=1, b=2, an executed trade creates one unit of gain; an offer rejected by either side creates none.

## Backstory

- 2017: Brustle and coauthors established the cited half-of-second-best guarantee.
- November 2021: Babaioff and coauthors displayed the 3/4 example and stated the remaining gap.
- March–October 2026: The cited neighboring work improved comparisons against first-best gains.

## Why it matters

A one-sided quote maximizes the offerer’s profit rather than the value created by trade. The question measures how much even the better quoting side can lose relative to a mechanism that still respects private information and participation.

## Real-world uses

An explicit example can test proposed bilateral trading rules or illustrate why a monopoly quote may reject mutually beneficial trades. It is a model comparison, not a trading-profit forecast.

## How to think about it

Tie-breaking is decisive. On the cited seller {0,1}, buyer {1,2} uniform example, the ratio is 3/4 under adverse ties but 1 under trade-favorable ties. A robust counterexample must survive the latter. Search can vary small support distributions and compare the two offers against a posted price or an incentive-compatible allocation.

## What counts as a solution

Give rational supports and probabilities, plus either a posted-price M or explicit allocation probabilities and interim transfers. Independently check every incentive and participation constraint and expected budget balance in exact arithmetic. Compute SO and BO with the largest GFT among tied profit-maximizing offers, then prove the strict inequality. Any positive improvement certified exactly counts. GFT_M only lower-bounds second-best; that suffices. Calibrate the checker on both tie conventions of the cited example and the supplied 2026 instance. Compare any later second-best results before claiming.

The numerical first-best partial bar is separate. Match printed calibration numbers within one unit of the last printed digit.

## Our approach

Search small independent value distributions and solve for a feasible comparison mechanism. Independently check all incentive inequalities and score offer ties conservatively in exact arithmetic.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/abs/2111.07790>
- <https://arxiv.org/pdf/2111.07790>
- <https://arxiv.org/pdf/2603.08679>
- <https://arxiv.org/abs/2607.13959>
- <https://arxiv.org/abs/2609.37997>
- <https://arxiv.org/pdf/2610.06547>
- Status source: <https://export.arxiv.org/api/query?search_query=abs:%22bilateral%20trade%22&sortBy=submittedDate&sortOrder=descending&max_results=50>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
