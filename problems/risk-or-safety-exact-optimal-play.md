# Exact odds for a push-your-luck coin race

**Open problem.** Two players race to n points by choosing whether to bank a run of heads or risk losing it. Find the exact optimal-play starting-player win probability for every target n=31,…,45, extending the supplied numerator and denominator sequences.

**Status.** Jehn’s March 2026 paper derives analytical small cases and reports strategy computations through n=20. The OEIS sources were unavailable, so their exact sequence frontiers and the novelty of the proposed range are not confirmed here. [Status source](<https://oeis.org/A387261>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. Terms n = 16..30 were merged in V3R1T4S PR #169. The open extension range starts at n = 31. This supplied repository-status update does not claim that OEIS has incorporated the terms. This preparation made no new source request.

## The problem

A head adds an open point. After a head, the player can stop and bank the open points or toss again. A tail discards the open points and passes the turn. At zero open points a toss is compulsory; reaching n with banked plus open points wins. For example, with one open point the choice is between keeping that point now and risking it for another head.

## Backstory

- March 2026: Jehn’s cited paper proved uniqueness of the optimal solution, derived small cases and reported larger strategy computations.

## Why it matters

The game isolates a recurring risk decision: whether to lock in an accumulated gain or expose it to another uncertain step. The optimal choice depends on both players’ progress, not only the current run.

## Real-world uses

Exact value and action tables can compare banking heuristics and benchmark stochastic-game solvers without sampling uncertainty.

## How to think about it

Banked totals never fall, but turns can alternate without progress. A numerical policy can suggest the right actions; exact evaluation must resolve close choices and certify the unique Bellman solution.

## What counts as a solution

For every n=31,…,45, supply reduced P(0,0,0) and value/action tables P(a,b,c), where a is open points, b the mover’s bank and c the opponent’s bank. Set P=1 when a+b≥n. Otherwise continue=(1/2)(1−P(0,c,b))+(1/2)P(a+1,b,c) and stop=1−P(0,c,a+b). At a≥1 check P=max(continue,stop); at a=0 check the forced toss. Independently verify all equations and action choices in exact arithmetic, reproduce earlier available exact values, including merged n=16,…,30, and use the source’s uniqueness argument. Establish the prior-work comparison before claiming new terms. Certified n=31,…,35 alone is partial progress; n=16,…,30 is already merged and does not count as an extension.

## Our approach

Find candidate policies by score-state decomposition, then solve and improve them exactly. Independently verify every Bellman equality and the full requested range of starting probabilities.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2603.01002>
- <https://arxiv.org/pdf/2603.01002>
- <https://oeis.org/A387261> — HTTP 403; not retrieved.
- <https://oeis.org/A387262> — HTTP 403; not retrieved.
- <https://oeis.org/A394776> — HTTP 403; not retrieved.
- <https://oeis.org/A387260> — HTTP 403; not retrieved.
- Repository status update supplied for this preparation: <https://github.com/elder-plinius/V3R1T4S/pull/169>.
