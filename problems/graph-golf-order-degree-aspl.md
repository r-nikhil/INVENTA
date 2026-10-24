# Better graphs for short network paths

**Open problem.** With a fixed number of vertices and a limit on connections per vertex, how short can network paths be? Improve an eligible Graph Golf 2021 graph first by diameter and, only at equal diameter, by exact average shortest path length.

**Status.** The archived 2021 rankings list Team RK, EvbCFfp1XB, D. Shimizu, SDKY-NITTYM and MODAL-Team among the entrants. The competition is closed; a proposed mathematical improvement must be compared with the archived graphs and any later published constructions. [Status source](<http://research.nii.ac.jp/graphgolf/ranking.html>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

General graphs must be simple, connected and undirected, with exactly n vertices and every degree at most d. Diameter is the largest shortest-path distance; ASPL is the sum of pair distances divided by the number of pairs. In the host-switch variant, each host has exactly one edge to a switch and each switch has at most r ports. As an ordering example, diameter three always beats diameter four even if its average distance is larger.

## Backstory

- 2015–2021: The cited Graph Golf competition ran.
- 2021-10-11: The input dates its final ranking update.
- 2024-01-09: The input dates a later site update.

## Why it matters

Interconnection networks face a tradeoff between limited ports and short communication paths. The graph problem isolates hop count from other engineering factors such as traffic load and cable length.

## Real-world uses

Explicit graphs can serve as candidate network topologies or reproducible benchmarks for topology optimization. Host-switch graphs directly encode endpoint and port constraints.

## How to think about it

Edge swaps may shorten many paths while lengthening a few that determine the diameter. Structured graphs can provide strong starting points. Exact distance sums matter because the displayed five-decimal averages can hide improvements or ties.

## What counts as a solution

Provide an edge list for an eligible 2021 featured cell, excluding the already optimal n40d5 and n432d12 cells. Independently verify simplicity, connectivity, vertex/host counts and degree or port bounds. Compute all required distances and the exact rational average for both candidate and published incumbent edge files. The candidate’s (diameter,ASPL), or host-only pair, must be lexicographically strictly smaller and beat any later published graph. A tie or a better average at worse diameter does not count.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

## Our approach

Improve archived graph constructions through degree-respecting changes and structured seeds. Independently recompute full shortest-path distances and compare exact ratios.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <http://research.nii.ac.jp/graphgolf/>
- <http://research.nii.ac.jp/graphgolf/problem.html>
- <http://research.nii.ac.jp/graphgolf/rules.html>
- <http://research.nii.ac.jp/graphgolf/ranking.html>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
