# What is the value of four-player continuous Guts?

**Open problem.** What is the exact four-player recursive coalition value?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2208.02788>).

## The problem

Player 1 faces a coordinated coalition of three opponents in continuous Guts. Determine the exact value under the paper’s recursive-game convention, with a unit ante and termination fee -1.

## Backstory

Kevin Buck, Jae Hwan Lee, Jacob Platnick, Aric Wheeler and Kevin Zumbrun’s 2022 paper gives numerical multiplayer results. Kevin Buck, Jessica Babyak, Leah Dichter, David Jiang and Kevin Zumbrun’s 2024 follow-up gives analytical three-player best-response formulas, including a small-continuation-value recursive analysis. The four-player value remains the target.

## Why it matters

A coalition can exploit a player even when individual deviations offer no gain. Repeated play adds another difficulty: losing holders replenish a pot whose stakes can grow.

## Real-world uses

The model provides a benchmark for coalition-game solvers and for rigorous analysis of games with increasing stakes.

## How to think about it

Hands are independent uniform numbers. Players hold above thresholds, and the coalition may correlate its threshold choices. The 2022 Table 1 reports coalition return 0.0339 for three opponents in a discretized pseudo-bloc computation. This is a numerical observation, with the opposite sign for player 1, rather than an exact unrestricted value.

## What counts as a solution

Give a symbolic value and strategies with exact global saddle inequalities, plus a proof that the recursion starting at -1 reaches that value. A fixed-point residual or a reduced pseudo-bloc solution alone is insufficient. The one-shot unrestricted value is an enumerated partial win.

## Our approach and status

Use numerical support guesses, reconstruct the payoff polynomials, and certify every threshold chamber and recursive tail. Printed-table calibration uses the same experiment and tolerance within one unit of the last printed digit. No new value is claimed.

## Sources

- <https://arxiv.org/pdf/2208.02788>
- <https://arxiv.org/pdf/2412.19855>
