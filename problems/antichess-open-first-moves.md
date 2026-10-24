# Settle an unresolved antichess opening

**Open problem.** In antichess, giving away your pieces is the objective. After which opening moves can either side force a win? The target is a forced-win proof after one of 1.a4, 1.b3, 1.c4, 1.g3, 1.g4 or 1.Nh3, valid under both of the specified stalemate rules.

**Status.** Watkins’s page confirms a winning 1.e3 strategy under both International and FICS rules. The six target openings come from the supplied proposal; this check did not establish that all six are still unresolved. [Status source](<https://en.wikipedia.org/wiki/Losing_chess>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

Captures are compulsory. Kings are ordinary capturable pieces; there is no check or castling, and a pawn may promote to a king. A player wins by losing every piece. Under International rules, the stalemated player wins; under FICS rules, the player with fewer pieces wins a stalemate, with equal counts drawn. Repetition and the fifty-move rule matter. For example, an available capture can force a player to take a piece even when doing so helps the opponent.

## Backstory

- 2015: Klaas Steenhuis solved 1.a3 as a Black win.
- October 2016: Watkins weakly solved antichess through a winning 1.e3 strategy.
- April 2019: Watkins documented a double-en-passant tablebase bug and a verifier fix; a verification must also address the affected tablebase leaves.
- 2020: Steenhuis supplied the cited 1.Na3 proof.

## Why it matters

Antichess turns familiar strategic instincts upside down and makes forced sequences central. Its computational value is a demanding test of whether a huge game-tree claim can be independently checked.

## Real-world uses

A solved opening supplies a guaranteed strategy and verified training positions. Its proof also tests move generators, transposition handling and endgame databases.

## How to think about it

A winning strategy needs one suitable choice whenever the winner moves and must cover every legal reply by the loser. Forced captures and transpositions can compress the tree. Endgame tablebases save search only when their answers are themselves trustworthy.

## What counts as a solution

For an opening still unresolved at verification time, provide a complete winning proof accepted by Watkins’s unmodified verify_win.c with the April 2019 fix, under both International and FICS stalemate rules. Resolve every tablebase leaf using rebuilt fixed tablebases, independently generated tablebases, or explicit terminal expansion. An independent move generator must agree on all leaves and a random 1% of internal nodes. A proof under one ruleset is only the proposal’s labelled partial result; an engine evaluation is not a proof.

## Our approach

Search forced capture lines and transpositions into verified positions. Export a proof tree and independently check the move rules and endgame leaves.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://en.wikipedia.org/wiki/Losing_chess> — HTTP 403; not retrieved.
- <https://magma.maths.usyd.edu.au/~watkins/LOSING_CHESS/>
- <https://magma.maths.usyd.edu.au/~watkins/LOSING_CHESS/LCsolved.pdf>
- <https://chessprogramming.org/Losing_Chess> — HTTP 403; not retrieved.
