# How many equilibria can binary choices create?

**Open problem.** Even when every player has only two actions, a game can have many stable patterns of play. Let μ(n;2,…,2) be the maximum number of Nash equilibria in a generic n-player binary-action game. Can a four-player game have at least 39 equilibria, contradicting the conjectured maximum of 37?

**Status.** Hertling and Vujić’s cited version gives a four-player lower bound of 37 and cites Vidunas’s upper bound of 65. For five players its formula gives (326+44)/2=185, while its table prints 187. The proposal’s target of at least 189 exceeds both figures. [Status source](<https://arxiv.org/abs/2412.17890>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

A Nash equilibrium lets no player improve by changing their own strategy alone. A mixed strategy chooses action 1 with a probability between zero and one. At a mixed equilibrium the player is indifferent between their two actions; a pure player must prefer the chosen action. “Generic” here requires regular isolated equilibria: the relevant indifference Jacobian is nonsingular and unused-action comparisons are strict. Counting tied or continuous families would change the problem. For example, a four-player support pattern (mix,0,1,0) requires indifference for the first player and strict best-response checks for the other three.

## Backstory

- 1997: McKelvey and McLennan established the derangement-number bound for totally mixed equilibria.
- 2017: Vidunas gave the cited overall upper bound.
- 2024: Jahani and von Stengel settled the three-player maximum at 9.
- 2024-12-23 and 2026-09-25: Hertling and Vujić’s cited versions developed the construction and conjecture.

## Why it matters

Equilibrium multiplicity limits how much a game model predicts. For a market or strategic interaction, finding one equilibrium may leave many others unexplored. This question isolates that difficulty in a very small action space.

## Real-world uses

Explicit games with complete equilibrium lists can benchmark equilibrium solvers and reveal whether numerical methods miss stable outcomes near strategy boundaries.

## How to think about it

Some players may mix while others choose pure actions. Every such support pattern must be checked, and improving the count on one face can destroy equilibria on another. Numerical search can propose rational-payoff games, but exact root isolation must separate distinct solutions and certify regularity.

## What counts as a solution

Supply rational payoff tables for a generic four-player game with at least 39 equilibria, or a five-player game with at least 189. Enumerate all 3^n support patterns, solve their polynomial systems exactly, check all best-response inequalities and regularity, and reproduce the complete count with an independent enumerator. Compare any later published counts and the best valid composition of published games for the same player count, and disclose any composition. Generic counts must be odd. Alternatively, a rigorously checkable proof that μ(4;2,2,2,2) ≤ 63 is a full result. An explicit certified 37-equilibrium example is the proposal’s partial target.

## Our approach

Perturb structured games to search for additional equilibria, then enumerate all supports with exact algebra. Use a separate enumerator to validate completeness and regularity.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2412.17890>
- <https://arxiv.org/pdf/2412.17890v2>
