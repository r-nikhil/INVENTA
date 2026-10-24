# Does scaling every stack preserve elimination odds?

**Open problem.** If three gamblers all receive the same stack multiplier, do their elimination-order probabilities barely change? Find positive integers A,B,C, an integer n≥2 and an order σ for which |P_{nA,nB,nC}(σ)−P_{A,B,C}(σ)| ≥ 0.0004, refuting Diaconis–Ethier Conjecture 4.2(a).

**Status.** Diaconis and Ethier state the scaling conjecture and report discrepancies as large as 0.000383. The cited later asymptotic results concern a different claim from this finite-scale numerical inequality. [Status source](<https://export.arxiv.org/api/query?search_query=abs:%22gambler%27s%20ruin%22&sortBy=submittedDate&sortOrder=descending&max_results=50>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

While three players survive, choose a pair uniformly and transfer one unit by a fair coin flip. After the first elimination, the remaining pair plays ordinary fair ruin. σ lists eliminations first-to-last: 132 means player 1 goes out before player 3, leaving player 2 as winner. The conjecture compares exact finite games, such as a base triple and its doubled version, not merely their limiting proportions. The supplied exact example P_{1,1,2}(312)=1/14 can be compared with P_{2,2,4}(312) for the finite scale n=2.

## Backstory

- 2022: Diaconis and Ethier published exact and near-exact computations and the scaling conjecture.
- 2024: Denisov and Wachtel published asymptotic results with a convergence rate.
- 2026-10-14: The supplied research recorded no resolution of the 0.0004 inequality.

## Why it matters

Tournament stack models often assume that proportions matter more than unit size. This question puts a precise error threshold on that intuition in a fair unit-transfer model.

## Real-world uses

Certified comparisons can test elimination-probability calculators and expose the size of discrete-chip effects in simplified final-table models. They do not prove that ICM is exact.

## How to think about it

Small stacks can magnify discreteness, so they are natural candidates. Interior states satisfy linear averaging equations; after a bust, the two-player boundary probability is determined by the surviving stack ratio. Numerical rankings can guide search, but the final discrepancy needs rigorous arithmetic.

## What counts as a solution

Name a finite n and provide both probabilities as exact fractions or directed-rounding intervals whose separation proves the displayed inequality. An independent checker must rebuild the six equiprobable interior transitions and correct two-player boundaries. Calibrate by checking that all six elimination orders sum to one and by reproducing the cited P_{1,1,2}(312)=1/14. A certified discrepancy strictly above the numerical bar 0.000383 and below 0.0004 is partial progress, subject to later published comparisons. Calibration against printed table decimals allows one unit of the last printed digit; exact identities remain exact. A discrepancy only at an infinite scaling limit is insufficient.

## Our approach

Compare small base triples with finite scaled versions using absorbing-chain equations. Independently certify the most promising discrepancies with exact or rigorous interval solves.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2011.07610>
- <https://arxiv.org/pdf/2011.07610>
- <https://arxiv.org/abs/2212.11526>
- <https://arxiv.org/abs/2406.07878>
- Status source: <https://arxiv.org/search/?query=gambler%27s+ruin+three+players&searchtype=all&abstracts=show&order=-announced_date_first&size=25>
- Original proposal status source: <https://export.arxiv.org/api/query?search_query=abs:%22gambler%27s%20ruin%22&sortBy=submittedDate&sortOrder=descending&max_results=50> — no new retrieval in this preparation.
