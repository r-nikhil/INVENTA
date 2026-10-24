# Close a gap in financial optimization benchmarks

**Open problem.** Can a public asset-allocation or pricing model be solved better, with an independently verified result? The targets are to improve the feasible objective of saa_2 below 12.1613089 or pricing050 above −1813.829078 by the specified margin, or to certify one of the proposal’s remaining optimality gaps.

**Status.** The fetched instance pages list saa_2 point p4 at 12.1613089 and pricing050 point p1 at −1813.829078. Their strongest displayed solver bounds are 6.02323546 and −1534.3281 respectively. These are solver-reported bounds, not independently checked certificates; minlplib.solu instead reports the third-best solver bounds. [Status source](<https://www.minlplib.org/minlplib.solu>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

saa_2 minimizes funding in a scenario-based asset model. Five weights lie in [0,1] and sum to one, while compounded returns, liabilities and binary shortfall indicators impose constraints. pricing050 maximizes a linear objective subject to nonlinear product-pricing constraints. As a sign example, a feasible objective of −1800 would improve a maximization value of −1813.829078; the inequality goes the other way for saa_2.

## Backstory

- 2001-05-01: saa_2 was added to the library.
- 2004-10-26: Its cited best point p4 was added.
- 2024-03-25 and 2024-08-26: pricing050 and its cited point p1 were added.
- 2025: The listed solver bounds were updated.
- 2026-09-14: The input records a later library update.

## Why it matters

Financial and pricing models can have a good candidate solution without a proof that no better one exists. Separating feasible points from global bounds prevents a reported solver gap from being mistaken for economic opportunity.

## Real-world uses

A verified point is a concrete benchmark improvement. A global certificate can establish whether further search is needed and test optimization software against a fixed public model.

## How to think about it

Any reduction of the asset model must preserve all constraints linking its weights, funding variable and auxiliary variables. A proposed structural simplification of pricing050 needs a proof before it can support a global certificate. The library’s summary gap uses the third-best solver bound, so inspect individual bounds.

## What counts as a solution

For a point improvement, provide the current model’s .sol variables, exact binary choices and an objective gain exceeding 10^−6 max(1,|best|). Independently evaluate every bound and constraint with maximum absolute violation ≤ 10^−8, confirm with 50-digit arithmetic, reproduce the printed baseline within one unit of its last printed digit and reject a perturbed invalid point. Save the model hash, point, evaluator and reference snapshots. Separately labelled certificate targets include closing pricing050 within 10^−6|best|, improving saa_2’s certified lower bound above 6.02323546, or closing its relative gap to 10^−6. Every global bound needs a replayable proof, not a solver status line.

The displayed objectives are numerical bars. If an incumbent is reconstructed exactly, any strict improvement with exact feasibility and objective certificates counts.

## Our approach

Build independent evaluators for the original models, then search the asset weights or certify the pricing model’s structure. Validate any improvement or global bound against the exact instance and stated tolerances.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://www.minlplib.org/instances.html>
- <https://www.minlplib.org/instancedata.csv>
- <https://www.minlplib.org/minlplib.solu>
- <https://www.minlplib.org/bounddates.html>
- <https://www.minlplib.org/doc.html>
- <https://www.minlplib.org/index.html>
- <https://www.minlplib.org/download.html>
- <https://www.minlplib.org/saa_2.html>
- <https://www.minlplib.org/pricing050.html>
- <https://www.minlplib.org/gms/pricing050.gms>
- <https://www.minlplib.org/sol/pricing050.p1.sol>
- <https://www.minlplib.org/gms/saa_2.gms>
- <https://www.minlplib.org/sol/saa_2.p4.sol>
- <https://optimization-online.org/wp-content/uploads/2020/03/7681.pdf>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
