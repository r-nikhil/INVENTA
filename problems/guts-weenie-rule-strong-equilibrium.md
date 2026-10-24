# Does the Weenie rule protect the symmetric Guts threshold?

**Open problem.** Does the Weenie threshold resist every coalition for n >= 4?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2208.02788>).

## The problem

Fix player 1’s threshold at a=3^(-1/(n-1)). In continuous Guts with the Weenie rule, is their expected immediate payoff alpha nonnegative against every opponent threshold vector?

## Backstory

Kevin Buck, Jae Hwan Lee, Jacob Platnick, Aric Wheeler and Kevin Zumbrun prove the two- and three-player cases in Appendix B of their 2022 paper. Appendix B.3 reports numerical tests and explicitly conjectures the general inequality. The abstract’s broader wording must be read with that limitation.

## Why it matters

A small rule change may make a symmetric strategy resist coordinated opponents. Proving the inequality would explain this stronger protection in the stated model.

## Real-world uses

Exact payoff functions and global certificates can benchmark game-theory software and check numerical claims about coalition resistance.

## How to think about it

When everyone drops, the highest-hand player must match the pot. The alpha payoff includes virtual-ante adjustments as well as the cash transfers. Its all-drop event gives each player 1 and charges the highest-hand player n. This accounting is essential.

## What counts as a solution

Prove alpha>=0 for every n and every threshold vector, or give an n>=4 algebraic threshold vector with alpha<0. Certificates for all opponent thresholds at n=4 or n=5 are partial wins. A grid with no negative sample is insufficient.

## Our approach and status

Derive the piecewise polynomials from the event rules, then use exact algebraic sign checks or a chamber-wide nonnegativity certificate. No new inequality proof or negative witness is claimed.

## Sources

- <https://arxiv.org/pdf/2208.02788>
- <https://arxiv.org/pdf/2412.19855>
