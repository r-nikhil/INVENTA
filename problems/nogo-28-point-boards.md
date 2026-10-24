# Solve the next NoGo boards

**Open problem.** In NoGo, players place stones while keeping every group alive; the first player unable to move loses. Who wins from the empty 2×14 or 4×7 board with Black moving first? Either outcome counts if it comes with a complete independently checkable strategy.

**Status.** Müller’s fetched page reports that Du’s SBHSolver solved rectangular boards through 27 points and that the later CGTSolver extended one-row boards through 1×39. It does not list solutions for 2×14 or 4×7. Absence from that page does not rule out a later solution elsewhere. [Status source](<https://webdocs.cs.ualberta.ca/~mmueller/nogo/solving.html>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

A block is an orthogonally connected group of same-colour stones; a liberty is an adjacent empty point. Players alternate placing a stone on an empty point. Passing, capture and suicide are forbidden: after a legal move, every block of either colour still has a liberty. For illustration, the sole point on a 1×1 board cannot legally be filled, because the new stone would have no liberty.

## Backstory

- 2023: Du, Wei and Müller reported the SBHSolver rectangular-board results through 27 points.
- 2024: Du extended the one-row results through 39 points.
- 2025-09-05: The input dates Müller’s cited status-page revision to this day.

## Why it matters

The rules are short, but the strategic state space grows quickly. NoGo separates game-tree reasoning from probabilistic evaluation: a solved board demands a response to every legal defence.

## Real-world uses

A proof supplies an optimal strategy for that board and a reproducible benchmark for search, symmetry reduction and legal-move verification.

## How to think about it

Symmetries and repeated positions can reduce the work. Narrow boards may expose useful components, but any decomposition needs justification. An observed pattern across smaller rectangles is only a search hint, not a proof for the next size.

## What counts as a solution

For 2×14, 4×7 or another rectangle still absent from the solved list, provide a documented proof tree or directed acyclic graph. At the winner’s turns, include a legal winning move; at the loser’s turns, include every legal move. All leaves must leave the player to move unable to act. A checker sharing no code with the solver must verify all blocks’ liberties, transpositions and any symmetry merges. Report the certificate’s node count and hash. Rechecking an existing board is a separate partial target.

## Our approach

Search narrow-board states with symmetry-aware transposition storage. Independently regenerate legal moves and stream-check the resulting proof certificate.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://webdocs.cs.ualberta.ca/~mmueller/nogo/solving.html>
- <https://webdocs.cs.ualberta.ca/~mmueller/ps/2023/ACG_2023_NoGo.pdf>
