# Close the gap in the two-player hat puzzle

**Open problem.** Two players see each other’s infinite fair hat stacks and simultaneously select a position on their own stack. They win only if both selected hats are black. Is the optimal success probability V₂ equal to 7/20? The proposal targets either a strategy exceeding 7/20 or a universal upper bound strictly below 81/224.

**Status.** The cited papers give lower bound 7/20, achieved by recursive strategies including Carter–Reyes and Tiefenbruck’s, and upper bound 81/224 from Buhler and coauthors. Bouquet and coauthors report further strategies with value 7/20. The status-search URL was unavailable, so this is a cited-paper comparison rather than a complete current record search. [Status source](<https://export.arxiv.org/api/query?search_query=abs:Levine%20AND%20abs:hat&sortBy=submittedDate&sortOrder=descending&max_results=50>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. A candidate V_{2,4} = 89/256 from complete enumeration exists but has not been verified. It is not an established optimum or a record bar. This preparation made no new source request.

## The problem

A player’s choice cannot depend on their own hats. Finite h-hat strategies have exact scores obtained by counting wins among 2^(2h) configurations. For example, always selecting the first position gives probability 1/4. Finite scores lower-bound the infinite game. Upper bounds use a separate hint game defined by a balanced binary matrix, where every column contains equally many zeros and ones.

## Backstory

- 2021: Buhler and coauthors published the 81/224 matrix-hint upper bound and discussed larger matrices.
- 2025: Heilman and Tamuz gave a different, weaker Fourier-analytic upper bound.
- 2026-04-19: Bouquet and coauthors’ cited revision retained 7/20 and 81/224 as the bounds.

## Why it matters

The puzzle asks how two decisions can be coordinated when neither decision-maker sees the quantity that determines their own success. It is a precise test of the limits of shared rules without communication.

## Real-world uses

Explicit strategies and hint matrices benchmark cooperative-game search, exact counting and symmetry-aware impossibility proofs.

## How to think about it

Better lower bounds require a new strategy, while better upper bounds require ruling out every strategy in a sufficient relaxation. For a hint matrix M with m columns and rows r_i, the cited value is max over column partitions π of (1/m)E[max_i r_i·v], where v assigns an independent fair bit to each partition class. A search that finds no large-value partition does not upper-bound this maximum.

## What counts as a solution

Either provide a balanced 0/1 hint matrix and an exhaustive, independently checked rational certificate that its partition-game value is U<81/224, or give explicit finite or recursive strategies with exact success probability >7/20. Verify every partition bound and symmetry reduction in the upper-bound route. For recursive strategies, derive the complete renewal equations independently. Calibrate against the cited 81/224 matrix and 7/20 strategies, and compare later results. Exact finite-hat optima are useful partial targets but cannot upper-bound V₂. A complete-enumeration candidate V₂,₄=89/256 remains unverified; the cited 89/256 strategy lower bound does not establish equality as the optimum. The 16×30 hint-matrix value is another listed partial target. Compare direct published strategies and their best valid compositions, and disclose any composition.

## Our approach

Search compact balanced hint matrices and finite strategy tables. Independently certify all partition bounds or exact configuration counts, including recursive resets.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/1407.4711>
- <https://arxiv.org/pdf/1407.4711>
- <https://arxiv.org/abs/2508.01737>
- <https://arxiv.org/pdf/2508.01737>
- <https://arxiv.org/abs/2503.09042>
- <https://arxiv.org/abs/2208.06858>
- <https://oeis.org/A345255> — HTTP 403; not retrieved.
- Status source: <https://arxiv.org/search/?query=Levine+hat&searchtype=all&abstracts=show&order=-announced_date_first&size=25> — HTTP 429; not retrieved.
- Original proposal status source: <https://export.arxiv.org/api/query?search_query=abs:Levine%20AND%20abs:hat&sortBy=submittedDate&sortOrder=descending&max_results=50> — no new retrieval in this preparation.
