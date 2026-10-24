# Does alternating predictive regret matching converge?

**Open problem.** A game solver may look reliable in experiments without a guarantee that its average strategy approaches equilibrium. Does alternating predictive regret matching+ (PRM+), exactly as Algorithm 8 of the cited paper, have averaged-strategy duality gap tending to zero in every two-player zero-sum matrix game, starting from zero regrets and uniform strategies?

**Status.** Cai, Farina, Grand-Clément, Kroer, Lee, Luo and Zheng discuss the unresolved ergodic convergence of alternating PRM+ in the cited 2025 paper. Guarantees for their other update rules do not establish this claim for Algorithm 8. [Status source](<https://arxiv.org/abs/2311.00676>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

Regret measures how much better an action would have done against past play. Regret-matching methods convert accumulated regrets into action probabilities; the “+” operation clips negative cumulative values. Prediction and alternating updates change the recurrence. Ergodic convergence concerns uniformly averaged strategies, not the current strategy. The duality gap is the difference between the best response against the column strategy and the worst response against the row strategy; zero means equilibrium. For illustration, a sequence alternating between (1,0) and (0,1) has no last-strategy limit, but its average approaches (1/2,1/2). Whether that average is an equilibrium depends on the game.

## Backstory

- 2015: Tammelin and coauthors described CFR+, whose matrix-game core uses alternating RM+.
- 2021: The cited earlier work showed last-iterate divergence of RM+ in rock-paper-scissors; this is distinct from failure of averaged-strategy convergence.
- 2025: Cai and coauthors published the stated open question and numerical last-iterate failures for related algorithms.

## Why it matters

Poker solvers rely on repeated updates to produce strategies with small exploitable weaknesses. A convergence theorem explains when more iterations eventually suffice; a counterexample identifies a real limitation of the exact update rule.

## Real-world uses

A proof can justify stopping and averaging choices in solver design. A certified counterexample supplies a reproducible regression benchmark for future regret-minimization methods.

## How to think about it

Clipping makes the dynamics piecewise rather than smooth. An apparently stable cycle can drift over longer runs. The source’s matrix A=[[3,0,−3],[0,3,−4],[0,0,1]] is a concrete starting example for related last-iterate questions; numerical behavior there does not answer the average-convergence question for alternating PRM+.

## What counts as a solution

Either provide a machine-checked universal convergence proof for Algorithm 8 under the stated initialization and uniform averaging, or give a rational matrix whose averaged gap provably fails to tend to zero. A counterexample may use a machine-checked proof or a fully written computer-assisted argument with every computation independently reproduced in exact or rigorous interval arithmetic. Formal proofs must have no admitted gaps or extra assumptions replacing the claim. The separate partial target is a proved positive liminf of the last-iterate gap for the specified RM+/PRM+ variants on A. Long simulations alone do not qualify.

## Our approach

Study exact clipping patterns and invariant regions in small matrix games. Convert any persistent behavior into an independently checked argument about the infinite update sequence.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2311.00676>
- <https://arxiv.org/pdf/2311.00676v2>
- <https://webdocs.cs.ualberta.ca/~games/poker/publications/2015-ijcai-cfrplus.pdf>
