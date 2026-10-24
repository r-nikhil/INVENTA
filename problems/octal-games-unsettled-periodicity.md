# Find a provable repeating pattern in an octal game

**Open problem.** Some simple heap games have been computed far into their sequences without a repeating pattern being proved. For an unsettled finite octal game in the cited table, find a preperiod n₀ and period p such that its Sprague–Grundy value satisfies G(n+p) = G(n) for every n ≥ n₀.

**Status.** Flammenkamp’s fetched table records unsettled games and credits Tyler Satchel Orden with July 2026 extensions. The fetched auxiliary list repeats .64; an eligible target must be identified unambiguously against the main table before a record claim. [Status source](<http://wwwhomes.uni-bielefeld.de/achim/octal.html>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

Octal digits encode legal heap moves. In digit d_i, bit 1 permits removing i tokens and leaving no heap, bit 2 permits one remaining heap, and bit 4 permits two nonempty heaps. A leading 4 permits splitting without removing tokens. For example, digit 3 permits the first two possibilities. G(n) is the least nonnegative integer absent from the values reachable from an n-token heap; two remaining heaps combine by XOR.

## Backstory

- 2002-05-21: The input records the solution of .106, with period 328,226,140,474 and preperiod 465,384,263,797.
- 2012-10-29: It records the long-preperiod result for 4.404.
- July 2026: Orden extended several unsettled sequences.
- 2026-10-14: The supplied main-table update still listed unresolved games.

## Why it matters

A finite rule can generate a sequence whose long-run behavior is difficult to establish. Proving eventual repetition turns infinitely many heap sizes into a finite computable description.

## Real-world uses

A verified period permits exact evaluation of arbitrarily large heaps and supplies a test case for sequence generators, cycle detection and finite certificates for infinite claims.

## How to think about it

A repeated block is not enough: it may stop repeating later. Sparse structure can accelerate computation, but a proof must establish the required repetition window using the actual values. Rolling hashes may find candidates; they cannot certify equality.

## What counts as a solution

Choose an unsettled 0.ddd or 4.ddd game, excluding Grundy’s game and 0.6111…. Independently recompute exact values and certify a published sufficient condition. Under the quoted Guy–Smith criterion for P digits, require G(r+p)=G(r) for all n₀ ≤ r < 2n₀+p+P; for 4.ddd, justify applicability to splitting without removal. Alternatively use the stated sparse-space criterion with its independently derived parameters and even period. Match the published frequency statistics through the recorded range. Explicitly state the theorem and all hypotheses used.

## Our approach

Search for cycles in games with compact recurrence state, then independently regenerate the sequence. Verify a complete theorem-sufficient window before treating repetition as permanent.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <http://wwwhomes.uni-bielefeld.de/achim/octal.html>
- <http://wwwhomes.uni-bielefeld.de/achim/unsettled.txt>
- <http://wwwhomes.uni-bielefeld.de/achim/octal_two_power.txt>
- <http://wwwhomes.uni-bielefeld.de/achim/nim/stat_.36>
- <http://wwwhomes.uni-bielefeld.de/achim/nim/stat_.167>
- <http://wwwhomes.uni-bielefeld.de/achim/nim/stat_.6>
- <https://en.wikipedia.org/wiki/Octal_game> — HTTP 403; not retrieved.
- <https://arxiv.org/pdf/math/0501315>
