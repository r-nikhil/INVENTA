# A certified ceiling on selfish-mining revenue

**Open problem.** What fraction of accepted blocks can a strategic miner obtain in the specified selfish-mining model? With rushing parameter γ = 0, certify a universal revenue bound U ≤ 0.70099 at hash share α = 0.45, or U ≤ 0.90466 at α = 0.475, in the untruncated Sapirshtein–Sompolinsky–Zohar model.

**Status.** Sapirshtein, Sompolinsky and Zohar report upper bounds 0.70109 and 0.90476 for the stated parameters. Bar-Zur, Eyal and Tamar report achievable-side values 0.66894 and 0.80184. The proposed task concerns a tighter certified upper bound. [Status source](<https://export.arxiv.org/api/query?search_query=abs:%22selfish%20mining%22&sortBy=submittedDate&sortOrder=descending&max_results=50>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

The model tracks private and public branch lengths and fork status. A policy chooses whether to adopt, override, match or wait. Relative revenue REV is the attacker’s share of accepted blocks, not profit per unit of wall-clock time. For candidate ρ, accepted attacker and honest block counts x,y receive reward w_ρ(x,y)=(1−ρ)x−ρy. A negative upper bound on this average reward can certify that REV stays below ρ. For example, accepting one attacker block and no honest blocks gives transformed reward 1−ρ, while accepting one honest block alone gives −ρ.

## Backstory

- 2016: Sapirshtein and coauthors published the truncated-model upper and lower bounds.
- 2020: Bar-Zur and coauthors improved the numerical lower side and noted an early-stopping issue in the original code.
- July 2026: The cited threshold work studied a richer model, distinct from this revenue-bound target.

## Why it matters

A security analysis needs limits on every permitted strategy, not just the strategies found by a search. Such limits clarify the incentive guarantees of a precisely specified blockchain model.

## Real-world uses

A bound can benchmark selfish-mining analyzers and quantify model-specific revenue exposure. It does not establish a bound for changed networking assumptions or for time-averaged mining profit.

## How to think about it

Truncating long forks can underpay the attacker and produce only a lower bound. The required construction instead overpays at the boundary so that a finite model dominates the original. The difficult step is retaining that guarantee while tightening the numerical solution.

## What counts as a solution

Supply rational ρ=U, truncation T, and a gain g<0 with a bias vector h such that r_ρ(s,a)+∑P(s′|s,a)h(s′)−h(s) ≤ g for every allowed state–action pair of the paper’s over-paying model N_ρ^T. An independent checker must rebuild transitions and compensation rewards from the source, verify every inequality exactly or with outward-rounded intervals, and apply Proposition 3 to the infinite model. Reproduce the supplied calibration values and confirm that a value below a known achievable revenue cannot be certified. Beat any later applicable upper bound as well.

The upper bars are numerical, so their stated margins remain. Calibration against printed numbers uses tolerance within one unit of the last printed digit.

## Our approach

Construct the over-paying finite model and search for a tighter average-reward certificate. Rebuild the model independently and check every bound inequality with rigorous arithmetic.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/pdf/1507.06183>
- <https://arxiv.org/pdf/2007.05614>
- <https://arxiv.org/abs/2607.24415>
- <https://api.github.com/repos/nirenzang/Optimal-Selfish-Mining-Strategies-in-Bitcoin>
- <https://api.github.com/repos/roibarzur/pto-selfish-mining>
- Status source: <https://export.arxiv.org/api/query?search_query=abs:%22selfish%20mining%22&sortBy=submittedDate&sortOrder=descending&max_results=50>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
