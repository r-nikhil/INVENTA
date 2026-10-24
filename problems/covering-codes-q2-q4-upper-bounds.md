# Cover every outcome with fewer codewords

**Open problem.** How small can a collection of forecasts be while staying close to every possible outcome? K_q(n,R) is the minimum size of C ⊆ {0,…,q−1}^n such that every word is within Hamming distance R of a member of C. The target is a strictly smaller covering code for a still-open binary, ternary or quaternary table cell.

**Status.** Kéri’s fetched ternary table gives 71 ≤ K_3(6,1) ≤ 73 and credits the upper construction to Laarhoven, Aarts, van Lint and Wille. Maharaj’s cited abstract gives K_4(8,2) ≤ 256 and K_4(6,2) ≤ 48. The listed binary table was also retrieved; these tables do not by themselves establish a complete current frontier. [Status source](<https://old.sztaki.hu/~keri/codes/>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

Hamming distance counts coordinates at which words differ. With symbols representing the three outcomes of a match, a length-n word is a football-pool coupon. Radius one means every possible result has a coupon with at most one incorrect forecast. As a small illustrative binary example, {000,111} covers all length-three words within distance one: each word has either at least two zeros or at least two ones.

## Backstory

- 1989: The cited construction established the 73-word upper bound for K_3(6,1).
- 2007: Linderoth, Margot and Thain supplied its lower bound of 71.
- 2009–2011: The supplied proposal dates the relevant Kéri table files to this period.
- 2026: Marosi reported new bounds for larger alphabets; Maharaj improved the two quaternary cells above.

## Why it matters

This is the mathematics of guaranteed approximate coverage. In a pool, it limits how many different forecasts are needed to cover the outcome space; in computing, it studies how compactly a discrete space can be represented with bounded error.

## Real-world uses

A code is an explicit coupon list with a proved error guarantee, or a finite test set covering every input within a stated number of changed symbols. Coverage does not imply a profitable bet: prices and payouts are outside the model.

## How to think about it

Each codeword covers a ball, and overlapping balls can waste capacity. Structured constructions reduce search size but may impose avoidable overlap. The proposed fresh angle combines local replacement of codewords with exact coverage counts and symmetry-based search. A 72-word code for K_3(6,1) would improve the upper bound; it would not by itself decide between 71 and 72.

## What counts as a solution

Give distinct words for a cell in the input’s ranges: q = 2, n ≤ 33, 1 ≤ R ≤ 10; q = 3, n ≤ 14, 1 ≤ R ≤ 8; or q = 4, n ≤ 11, 1 ≤ R ≤ 8. The size must beat both Kéri’s bound and all later direct or implied bounds. Exhaustively verify coverage, preferably using both distance-ball marking and an independent coordinate-dilation check. Read the original table cell carefully and exclude closed perfect-code cells. A purported size below a certified lower bound signals a verification problem.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

## Our approach

Combine structured starting codes with local search driven by exact coverage counts. Check the complete outcome space independently and compare all bounds implied for the chosen cell.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://old.sztaki.hu/~keri/codes/>
- <https://old.sztaki.hu/~keri/codes/2_tables.pdf>
- <https://old.sztaki.hu/~keri/codes/3_tables.pdf>
- <https://old.sztaki.hu/~keri/codes/4-5_tables.pdf>
- <https://arxiv.org/abs/2608.19872>
- <https://arxiv.org/html/2608.19872>
- <https://arxiv.org/abs/2610.03760>
- <https://arxiv.org/abs/2511.02542>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
