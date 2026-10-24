# The fair margin in “Fill your basket”

**Open problem.** An opponent selects a basket; you then choose which remaining coin to place in it. At the end you take the largest basket and the opponent the second largest. Determine the exact optimal-play margin A392305(n) for every n=17,…,20, with coins worth 1 through n and three baskets.

**Status.** The listed OEIS sources could not be retrieved. The computation ranges below are targets from the supplied proposal; their current novelty was not established. [Status source](<https://oeis.org/A392305>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. The earlier page review was dated 2026-10-15. This preparation made no new source request.

## The problem

On each turn the presenter picks one of three baskets before the placer chooses a coin. The placer maximizes largest sum minus second-largest sum; the presenter minimizes it. That minimax margin measures the difference in basket payoffs under optimal play. For an illustrative terminal state (2,5,8), the margin is 3, while the largest basket itself is 8. Those are different objectives.

## Backstory

- 2025-12-12: Jehn’s related A391538 entry was added, drawing on the cited Game of Chests challenge by Niessen and Rathke.
- 2026-01-06: The “Fill your basket” A392305 entry was added.

## Why it matters

The game separates control of the destination from control of the amount committed. That makes it a small, fully specified model of adversarial allocation and fair compensation.

## Real-world uses

Exact margins quantify the payoff advantage and can be used to define compensation once its payment convention is specified. Strategy certificates also benchmark minimax solvers and show whether a proposed allocation rule withstands every opposing choice.

## How to think about it

The remaining coin set and all three basket sums matter; their total alone is insufficient. Sorting the sums removes equivalent basket labels. Decision searches can ask whether the placer guarantees a target margin, but a complete answer needs both a strategy achieving it and an opposing strategy preventing more.

## What counts as a solution

Give all four values A392305(17), …, A392305(20). For each, supply a placer table forcing margin ≥v and a presenter table forcing margin ≤v. An independent checker must exhaustively traverse all legal replies and confirm both guarantees with integer arithmetic, after reproducing the earlier available terms. Check the entry, b-file and history for prior terms. Computing only n=17,18 is partial; the related A391538 target requires two-sided certificates for n=15,…,22 and does not replace the margin-game result.

## Our approach

Search canonical remaining-coin and basket-sum states with exact minimax bounds. Independently replay both players’ strategy tables against every legal reply.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://oeis.org/search?q=%22Fill+your+basket%22&fmt=text> — HTTP 403; not retrieved.
- <https://oeis.org/search?q=id:A391537|id:A391538&fmt=text> — HTTP 403; not retrieved.
- <https://oeis.org/search?q=%22optimal+strategy%22+keyword:hard&fmt=text> — HTTP 403; not retrieved.
- Status source: <https://oeis.org/A392305> — HTTP 403; not retrieved.
