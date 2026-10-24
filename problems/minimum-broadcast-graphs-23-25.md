# Sparse five-round broadcast graphs on 23–25 vertices

**Open problem.** Can a 23–25-vertex graph improve the five-round broadcast edge bounds?

**Status.** Mohammadhossein Fakharan’s November 2025 Concordia PhD thesis, Dimensional Broadcast Schemes and Their Applications in Broadcast Graphs, section 1.3, printed pages 20–21, lists the remaining gaps through n=32: B(23) in {33,34}, B(24) in {35,36}, and B(25) in {38,39,40}. It credits earlier constructions and degree-based lower bounds, including Bermond and coauthors. In the synchronous telephone model, a simple undirected broadcast graph informs all vertices from every possible source in ceil(log2 n) rounds. Each vertex participates in at most one call per round. A call goes from an endpoint informed at the start of the round to an uninformed neighbor. All three cases allow five rounds.

Status checked: 2026-10-15 (supplied literature-status date; primary publication re-read 2026-10-24, later literature not independently rechecked). [Status source](<https://spectrum.library.concordia.ca/id/eprint/996508/1/Fakharan_PhD_F2025.pdf>).

## The problem

One informed vertex starts with a message. In each synchronous round every vertex can participate in at most one call. A graph qualifies only if every possible source can inform every vertex within five rounds.

## Backstory

Fakharan’s November 2025 thesis lists B(23) in {33,34}, B(24) in {35,36} and B(25) in {38,39,40}. It credits earlier sparse constructions and computational degree bounds.

## Why it matters

The graph must support fast broadcasting despite call contention. Diameter alone cannot certify this property.

## Real-world uses

The model studies communication topologies and message dissemination when each node handles one connection at a time. Its assumptions are an idealization of real networks.

## How to think about it

Search graph edges and all source schedules together. A newly informed vertex can call only in the next round. Symmetry can save search effort if its orbit argument is proved.

## What counts as a solution

Give a simple graph and explicit five-round broadcast schedules from every vertex, with either 23 vertices and at most 33 edges, 24 vertices and at most 35 edges, or 25 vertices and at most 39 edges. The first two possibilities settle the corresponding exact values using the published lower bounds; a 39-edge 25-vertex graph improves the record, while 38 edges settles B(25). Every source must have its own valid schedule. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar.

Check the graph has exactly n labeled vertices, no loops or parallel edges, and the claimed number of edges. For each of n sources initialize only that source as informed. In each round verify that each listed pair is an edge, pairs form a matching, and one endpoint was informed at the start of the round while the other was not. Update all calls simultaneously. After at most five rounds all n vertices must be informed. The entire certificate contains at most n(n−1) transmissions and is tiny.

## Our approach

Try edge deletion and rewiring from published graphs, or a joint SAT encoding. Expand certificates to every source and replay each round. No new graph is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://spectrum.library.concordia.ca/id/eprint/996508/1/Fakharan_PhD_F2025.pdf>
