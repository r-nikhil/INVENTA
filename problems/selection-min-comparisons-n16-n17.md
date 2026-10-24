# Selecting a median with fewer comparisons

**Open problem.** To find a middle value, must we first learn more of the ordering than we need? Let V_i(n) be the minimum worst-case number of pairwise comparisons needed to find the i-th smallest of n distinct elements. The headline question is whether V_8(16) = 28 or 29. Related targets are to improve the known upper bounds for V_6(17), V_7(17), V_8(17), and V_9(17).

**Status.** Cremer’s fetched README gives V_8(16) ≤ 29 and, for n=17 and ranks 6 through 9, upper bounds 29, 30, 31 and 31. The corresponding lower bounds for these five targets are 28, 28, 29, 29 and 29. These are the cited repository’s reported bounds. [Status source](<https://raw.githubusercontent.com/JCremerr/selection-7-of-16/main/README.md>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

A comparison tells us which of two elements is smaller. A decision graph chooses the next comparison from previous answers and eventually returns the requested element. The cost is the longest possible path, not the average over random inputs. For example, finding the smaller of two distinct values needs one comparison. Ranks are one-based: V_8(16) concerns the lower of the two central elements; reversing all orders gives V_i(n) = V_{n+1-i}(n).

## Backstory

- 1996: Gasarch, Kelly and Pugh published selection bounds.
- 2025: Dörrer and coauthors settled all entries through n = 15 and established lower bounds for the remaining n = 16 cells.
- 2026-10-13: Cremer reported V_7(16) = 28, improved the other listed upper bounds, and supplied decision graphs and verification tools.

## Why it matters

Selection is a basic computing operation behind order statistics. A worst-case guarantee matters when every comparison has a cost, including ranking observations used in trading analysis. The mathematical target measures comparisons only; it does not establish a faster end-to-end application.

## Real-world uses

A verified decision graph can be used as an exact selection routine for a fixed batch size, or as a benchmark for tools that synthesize and check algorithms.

## How to think about it

The search is a game against an adversary who chooses comparison outcomes consistent with earlier answers. Many histories describe the same partial order, so identifying equivalent states can save work. The proposal suggests proof-number search, better estimates for unsolved states, and alternative openings. Failure to complete one opening does not rule out all decision graphs; counting leaves alone cannot establish the desired stronger median lower bound.

## What counts as a solution

Supply a comparison decision graph for (n,i) in {(16,8),(17,6),(17,7),(17,8),(17,9)} whose worst-case cost is strictly below the best upper bound at verification time. Use the cited certificate format or a lossless conversion. Both Cremer’s static checker and an independently written checker must accept it, including rank adjustments and all possible comparison paths. A 28-comparison median-of-16 graph would match the lower bound and settle that cell. A stronger lower bound is a separate partial result requiring a checked proof object, or two reproducible independent exhaustive searches clearly labelled computational. Random testing and timeouts are insufficient.

## Our approach

Search decision graphs from alternative partial orders, with exact small-state bounds guiding the search. Independently propagate ordering constraints through every candidate certificate.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/abs/2610.18740>
- <https://arxiv.org/html/2610.18740>
- <https://raw.githubusercontent.com/JCremerr/selection-7-of-16/main/README.md>
- <https://drops.dagstuhl.de/storage/00lipics/lipics-vol338-sea2025/LIPIcs.SEA.2025.16/LIPIcs.SEA.2025.16.pdf>
- <https://raw.githubusercontent.com/JGDoerrer/selection_generator/main/README.md>
- <http://www.cs.hut.fi/~cessu/selection/> — HTTP 301; not retrieved.

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
