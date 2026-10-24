# Verify a three-player bluffing equilibrium

**Open problem.** A proposed poker strategy bluffs with weak hands, bets strong hands and checks the middle. Is the threshold profile in the cited three-player von Neumann game actually a Nash equilibrium at bet size b=2, against every measurable unilateral deviation?

**Status.** Krityakierne, Thanatipanonda and Zeilberger report conjectured thresholds A≈0.137058194328370, B≈0.829422249795391 and C≈0.641304115985175, with player-I value approximately 0.122557074714865. The proposal asks for verification of the global best-response inequalities, beyond the paper’s threshold equations. [Status source](<https://arxiv.org/abs/2407.16155>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. The earlier page review was dated 2026-10-15. A proof for every b > 0 under the simultaneous-callers rules was submitted in V3R1T4S PR #196 and closed on 2026-10-24 (proof claims need peer review). It is not an established proof or a record bar. This preparation made no new source request.

## The problem

Each player antes one and receives an independent uniform hand in (0,1). Player I checks for a three-way showdown or bets b. After a bet, players II and III call or fold without observing each other’s decisions. Highest remaining hand wins. The proposed rule bets when x<A or x>B and calls when the responder’s hand exceeds C. Thus a weak hand can bet as a bluff even though it would usually lose a showdown.

## Backstory

- 2024-07-23: The cited paper proposed the continuous threshold profile using finite-deck computations and three indifference equations.
- 2026-10-15: The earlier page review recorded no later full verification.
- 2026-10-24: an all-b>0 proof submitted in V3R1T4S PR #196 was closed without merging (the repository records only machine-checkable results, and a proof needs peer review) after the maintainer reproduced its closed forms and b = 2 value to 60 digits; this is not an established verification.

## Why it matters

Indifference at a cutoff is necessary for a mixed strategic boundary but does not prove that actions are optimal everywhere else. This is a small multiway-poker example where that distinction can be settled exactly.

## Real-world uses

A full certificate would provide a clean benchmark for continuous-game equilibrium verification and a precise teaching example of bluff and call ranges.

## How to think about it

Against threshold opponents, action values are piecewise polynomials in the player’s hand. Check their signs on every interval, not just at A, B and C. The observation structure is essential: allowing the third player to see the second player’s response defines a different game.

## What counts as a solution

At b=2, define A,B,C as exact real algebraic roots of the source’s equations A–C with isolating intervals. Independently verify all best-response inequalities over every hand and all measurable deviations, using exact symbolic or machine-checked reasoning. In the confirmation case, report the exact algebraic player-I value within one unit of the last printed digit of 0.122557074714865 (10^−15). Alternatively give a hand interval and profitable deviation certified with exact or rigorous interval arithmetic. The same checked result for all b>0, or a stated interval containing 2, is partial progress. The all-b simultaneous-callers proof in PR #196 remains under review. Finite-deck comparisons must use the source’s distinct-card dealing convention.

## Our approach

Derive piecewise action payoffs and isolate the threshold roots exactly. Independently check polynomial signs over the full hand range, including bluff and fold regions.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2407.16155>
- <https://arxiv.org/pdf/2407.16155>
- <https://www.math.ucla.edu/~tom/papers/poker2.pdf>
- Repository status update supplied for this preparation: <https://github.com/elder-plinius/V3R1T4S/pull/196>.
