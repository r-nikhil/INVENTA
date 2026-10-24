# How costly can the best stable shared network be?

**Open problem.** Three users choose routes and split the cost of every edge they share. Even the cheapest stable arrangement can cost more than a coordinated optimum. Can an undirected three-player instance have price of stability strictly greater than 1769/1126?

**Status.** Disser, Feldmann, Klimm and Mihalák’s cited paper reports lower bound 1769/1126 and the upper bound 286/175 credited to Bilò and Bove. The paper leaves the exact three-player value unresolved; this check does not establish a complete later-literature comparison. [Status source](<https://www2.mathematik.tu-darmstadt.de/%7Edisser/pdfs/DisserFeldmannKlimmMihalak15.pdf>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

Each player has a source and target and chooses a simple path in a graph with positive edge costs. If an edge costs c and two players use it, each pays c/2. A Nash equilibrium permits no cheaper unilateral path switch. Social cost counts each used edge once. Price of stability is the cost of the cheapest equilibrium divided by the minimum social cost over all profiles.

## Backstory

- 2008: The cited Anshelevich et al. paper describes this network-design setting.
- 2009: Christodoulou and coauthors supplied the earlier lower bound 74/48.
- 2011: Bilò and Bove proved the upper bound 286/175.
- 2013/2015: Disser and coauthors presented and published the improved five-vertex construction.

## Why it matters

Cost sharing can leave users in a stable but wasteful arrangement. Measuring the best equilibrium asks whether selecting a favorable stable outcome is enough to control that waste.

## Real-world uses

Small exact examples can stress-test shared-network pricing rules and equilibrium-selection procedures. They explain a limitation of equal cost splitting, without claiming to model every real network tariff.

## How to think about it

One expensive equilibrium is insufficient: a cheaper equilibrium would lower the ratio. Search must make every stable profile costly while keeping some coordinated profile cheap. The cited work shows that an argument using only potential-minimizing equilibria cannot close the full gap.

## What counts as a solution

Give an undirected graph with positive rational edge costs and exactly three source–target pairs. Enumerate every simple path and every strategy profile, check all unilateral deviations with exact fractions, and compute the cheapest equilibrium and social optimum. Their exact ratio must exceed 1769/1126 and all later published three-player lower bounds. Two independently written checkers must agree. Reproducing the published construction is a baseline partial result, not a new record.

## Our approach

Search small graph topologies and rational edge costs for instances with costly equilibria. Independently enumerate all paths and profiles to certify the minimum equilibrium ratio.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://www2.mathematik.tu-darmstadt.de/%7Edisser/pdfs/DisserFeldmannKlimmMihalak15.pdf>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
