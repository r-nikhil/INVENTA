# Exact values for hidden-information game benchmarks

**Open problem.** How much can perfect play guarantee in a small game with hidden information? Determine an exact rational Nash value for classical Phantom Tic-Tac-Toe, Abrupt Phantom Tic-Tac-Toe, 3×3 Abrupt Dark Hex, or two-dice five-face Liar’s Dice, using the precise implementations cited in the proposal.

**Status.** Rudolph and coauthors’ table reports PTTT 0.66665 ± 0.00026, APTTT 0.55017 ± 0.00014, ADH3 0.38443 ± 0.00021 and LD2D5F 0.01770 ± 0.00018. These are approximate benchmark values. Ordinary 3×3 Dark Hex is listed with exact value 1 and is excluded from this target. [Status source](<https://arxiv.org/abs/2502.08938>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

An information state collects histories a player cannot distinguish, so the strategy must choose the same action distribution throughout that state. Payoffs are +1 for a win, −1 for a loss and 0 for a draw. Collision rules matter: a hidden occupied-cell attempt is retried in the classical variant but loses the turn in the abrupt variant. For strategies σ₁,σ₂, let L=min_τ₂ u₁(σ₁,τ₂) and U=max_τ₁ u₁(τ₁,σ₂). Then L ≤ value ≤ U.

## Backstory

- Fall 2024: The cited Phantom Tic-Tac-Toe challenge used abrupt collision rules.
- 2026: Rudolph and coauthors published benchmark values and exploitability tools.
- 2026-05-27: The supplied proposal pins its table comparison to version 4 of that paper.

## Why it matters

An exact benchmark distinguishes solver error from uncertainty about the game’s true value. The same hidden-information discipline is central to poker: a best response cannot inspect cards or board information unavailable to the player.

## Real-world uses

Verified values and strategies can test learning algorithms, independent best-response code and claims of reduced exploitability.

## How to think about it

The boards are small but the history and information-state spaces are large. Approximate strategies can suggest a small exact support; probabilities then need rational reconstruction and full best-response checks. A plausible fraction inside a numerical interval is only a conjecture.

## What counts as a solution

Provide valid rational action probabilities at every information state. Pin exp-a-spiel to commit 9412882c24e521fad7cbd96fdd68311d9bf6f203 or a named later commit for the board games; use the paper’s OpenSpiel liars_dice settings numdice=2 and dice_sides=5 for LD2D5F. An independent exact checker must establish L=U and report the reduced fraction within the supplied interval. A rigorously verified enclosure U−L ≤ 10^−6 is a partial result. For printed reference values, allow one unit of the last printed digit in calibration; exact strategy validity and L=U still require exact equality. Include rounding-error control for any interval route, and compare the sum of per-player exploitabilities, not one seat alone.

## Our approach

Use approximate solving to identify candidate supports, then reconstruct rational strategies. Independently compute complete best responses under the pinned information and collision rules.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2502.08938>
- <https://arxiv.org/pdf/2502.08938>
- <https://github.com/gabrfarina/exp-a-spiel>
- <https://github.com/nathanlct/IIG-RL-Benchmark>
- <https://www.mit.edu/~gfarina/6S890/challenge.html>
- <https://live.ocw.mit.edu/courses/6-s890-topics-in-multiagent-learning-fall-2024/mit6_s890_f24_tic-tac-toe.pdf>
