# A tighter equilibrium for three-player jam-or-fold poker

**Open problem.** How close to equilibrium can a complete three-player tournament endgame strategy be? For the specified jam-or-fold model, find a stationary strategy profile whose maximum unilateral improvement is at most $0.0010 from a $100 prize pool, across every starting stack state and every player.

**Status.** Ganzfried and Sandholm’s 2008 paper reports a maximum deviation gain of $0.0488 for its tournament model. The proposal requests a stronger bound for that model and requires evaluation under both of its explicitly specified same-hand elimination conventions. This check does not establish a current best-record claim. [Status source](<https://www.ijcai.org/Abstract/09/034>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

There are 13,500 chips, blinds 300/600, no antes, stacks in 300-chip units and 946 nonterminal stack vectors. Positions rotate each hand. Players use 169 preflop hand classes and can jam, call or fold as applicable. Payouts are $50/$30/$20; states with at most two nonzero stacks use Independent Chip Model terminal values. If a pot split leaves an indivisible 300-chip unit, a tied player receives it at random. ε is the largest best-response gain, not the average gain or a per-hand number. For illustration, if one state lets a player improve by $0.01, the profile fails the $0.0010 target even if every other state is already an equilibrium.

## Backstory

- 2008: Ganzfried and Sandholm described the tournament model and reported the ε bound.
- 2009: Their later work developed the policy-iteration approach.
- 2015: Ganzfried’s thesis specified the terminal and best-response evaluation in Section 9.4.
- 2026: The cited later work reused the state structure with different payouts.

## Why it matters

Tournament prizes are nonlinear in chip stacks. A strategy that is difficult to exploit in chips need not be equally safe in prize money, especially around elimination and side pots.

## Real-world uses

A verified profile benchmarks multi-player equilibrium solvers and provides a reproducible comparison with ICM-valued endgame decisions for this restricted game.

## How to think about it

Each player’s deviation problem spans future hands and rotating positions. Exact card removal, short-stack blinds and side pots affect transitions. The induced decision process is undiscounted, so the correct minimal nonnegative value solution matters.

## What counts as a solution

Provide action probabilities for every stack vector, hand class and decision situation. Enumerate actual cards and boards for exact all-in outcome probabilities. Independently compute profile values and each player’s best response, taking the maximum gain over all states and players. Prove ε ≤ $0.0010 under both elimination rules: larger starting stack takes the higher place with ties sharing prizes; or all same-hand eliminations share their prizes equally. A certified ε strictly below $0.0488 but above $0.0010 is a partial result. Keep the source’s blinds, payouts, random chip allocation and terminal ICM convention.

Use exact arithmetic or rigorous intervals for strategy values and best-response values. Small numerical residuals alone do not certify epsilon.

## Our approach

Build an independent ex-post deviation evaluator, then improve the stationary profile using state-level equilibrium solving and policy iteration. Check the complete bound under both elimination conventions.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://aamas.csc.liv.ac.uk/Proceedings/aamas08/proceedings/pdf/paper/AAMAS08_0313.pdf>
- <https://www.ijcai.org/Abstract/09/034>
- <https://www.ijcai.org/Proceedings/09/Papers/034.pdf>
- <https://www.csd.cmu.edu/sites/default/files/phd-thesis/CMU-CS-15-104.pdf>
- <https://arxiv.org/abs/2608.09586>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
