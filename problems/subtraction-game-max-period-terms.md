# The longest repeating subtraction game

**Open problem.** A subtraction game allows removing only specified numbers of tokens from a heap. Its eventual pattern repeats, but how long can the minimal period be? Extend A389689 at n = 24 or A389690 at n = 23, maximizing over every move set S ⊆ {1,…,n} that contains n.

**Status.** The listed OEIS entries and accompanying files could not be retrieved. The next-term targets below come from the supplied proposal; their novelty and the current sequence frontiers are unconfirmed. [Status source](<https://oeis.org/A389690>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

A player removes s ∈ S tokens without making the heap negative; no legal move means a loss. The outcome sequence records win or loss. The Sprague–Grundy sequence records the least nonnegative integer absent among reachable values. For example, with S={1}, both sequences alternate between their two possible values and have period two. The target uses the smallest eventual period, after any initial irregular segment.

## Backstory

- 1966: Golomb established eventual periodicity for finite subtraction games.
- 1995: Althöfer and Bültermann gave move sets with cubic periods.
- 1997: Flammenkamp conjectured an at-most-quadratic period bound for three-move sets.
- October 2025: Yao’s cited maximum-period sequences were recorded.

## Why it matters

Short rules can create long strategic cycles. Exact extremal examples help distinguish observed patterns from general claims about how complicated finite-memory games can become.

## Real-world uses

New terms provide benchmarks for cycle detection and exact enumeration. Maximizing move sets also supply examples against which proposed period-growth bounds can be tested.

## How to think about it

Finding one long-period set only proves a lower bound on the maximum. Exactness requires every eligible set. Grundy values can be as large as |S|, so use ceil(log₂(n+1)) bits per entry rather than a fixed four bits at these n. The full window of the previous n values determines the next value, so cycle detection must use that complete state. The maxima need not increase with n.

## What counts as a solution

For a target confirmed to be unlisted at verification time, give a maximizing S and have an independent program recompute its minimal eventual period. Two independently written exhaustive searches over all 2^(n−1) eligible sets must agree on both the maximum and the entire histogram of periods. Reproduce smaller published terms and check the entry, b-file and history before claiming novelty. A larger period contradicting an existing listed maximum is the proposal’s correction target.

## Our approach

Enumerate move sets with compact recurrence states and exact cycle detection. Independently reproduce the complete period histogram and every claimed maximizing example.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://oeis.org/A389689> — HTTP 403; not retrieved.
- <https://oeis.org/A389690> — HTTP 403; not retrieved.
- <https://oeis.org/A389689/a389689_1.txt> — HTTP 403; not retrieved.
- <https://oeis.org/A389690/a389690_2.txt> — HTTP 403; not retrieved.
- <https://arxiv.org/abs/2601.18715>
