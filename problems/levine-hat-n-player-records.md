# Coordinate more players in Levine’s hat puzzle

**Open problem.** Each player sees everyone else’s hats but cannot see their own. Can a team of n=3,…,12 players improve the published probability that every player selects a black hat from their own stack, using an explicit independently verified strategy?

**Status.** Buhler and coauthors’ Section 5 gives the n-player reference table, including 9119/32670 for n=3 and 14844/64120 for n=4, attributed to Reyes and Carter’s 2014 searches. Larger-n entries use generalized Winkler strategies. The status-search URL was unavailable, so later improvements were not ruled out. [Status source](<https://export.arxiv.org/api/query?search_query=abs:Levine%20AND%20abs:hat&sortBy=submittedDate&sortOrder=descending&max_results=50>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

Every stack consists of independent fair black/white hats. Choices are simultaneous and may depend only on other players’ hats. V_n is the supremum team success probability. A t-level strategy is a finite table mapping visible t-hat stacks to one of the player’s own levels. For an illustrative baseline, if everyone always names the first level, independence gives success probability 2^−n. Recursive strategies may skip tiers, requiring full renewal bookkeeping.

## Backstory

- 2014: Reyes and Carter searched symmetric strategies for the three- and four-player records.
- 2021: Buhler and coauthors published the cited lower-bound table.
- 2022: The cited later work addressed structural properties of V_n.
- 2025–2026: The follow-up papers identified in the input focus on two players.

## Why it matters

Seeing more information is not the same as being able to communicate it. The puzzle isolates coordinated decisions when every participant is missing a different part of a shared random state.

## Real-world uses

Finite strategy tables give exact benchmarks for decentralized decision algorithms. They can test whether an implementation accidentally lets a player inspect its own hidden information.

## How to think about it

The earlier searches imposed symmetry, so asymmetric tables are a natural search direction. Changing one table entry affects only configurations with that visible view. Recursive resets can improve a finite table, but different players may reset at different tiers.

## What counts as a solution

Give a t-level strategy for some n∈{3,…,12}, optionally with explicitly derived recursive resets. Enumerate all 2^(nt) tier configurations and solve renewal equations exactly with an independent evaluator. Beat the source’s exact fraction for n=3,…,8. For n=9,…,12, reach at least 0.158765, 0.153518, 0.149026 or 0.145048 respectively, unless the exact construction value is recovered and strictly beaten. These margins account for rounded-down source decimals. Also compare later published records and the best valid composition of published strategies. Disclose whether the submitted strategy is a composition and cite its components. A certified upper bound V₃<89/256 is the listed partial target. Verify that no action uses its owner’s hats.

## Our approach

Search asymmetric finite strategy tables using exact incremental scores. Independently enumerate all configurations and derive any mixed-tier reset probabilities.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/1407.4711>
- <https://arxiv.org/pdf/1407.4711>
- <https://arxiv.org/abs/2208.06858>
- <https://arxiv.org/abs/2508.01737>
- Status source: <https://arxiv.org/search/?query=Levine+hat&searchtype=all&abstracts=show&order=-announced_date_first&size=25> — HTTP 429; not retrieved.
- Original proposal status source: <https://export.arxiv.org/api/query?search_query=abs:Levine%20AND%20abs:hat&sortBy=submittedDate&sortOrder=descending&max_results=50> — no new retrieval in this preparation.
