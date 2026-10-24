# Can an independent Guts coalition force a loss?

**Open problem.** Is the asynchronous coalition value zero for all n >= 4?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2412.19855>).

## The problem

In the one-shot continuous Guts payoff game, can n-1 opponents who randomize independently force player 1’s best response below zero? The conjecture says they cannot, for every n>=4.

## Backstory

Kevin Buck, Jessica Babyak, Leah Dichter, David Jiang and Kevin Zumbrun establish the three-player result in their 2024 paper. Remark 5.9 and Section 9.1 explicitly conjecture its extension to n players.

## Why it matters

Independent and coordinated opponents have different powers. This question isolates how much coalition advantage depends on shared random choices.

## Real-world uses

The model can test optimization methods for product distributions and compare assumptions about communication in strategic systems.

## How to think about it

Each opponent chooses a probability law on hold thresholds. Their joint law must be the product of those laws. First fix these laws, then let player 1 choose a best response. A symmetric Nash profile gives an upper bound of zero; the unresolved part is proving that every product law permits a response worth at least zero.

## What counts as a solution

Prove the conjecture for arbitrary independent laws and every n>=4, or give one set of laws whose entire best-response curve is strictly negative. Finite rational or algebraic supports permit exact polynomial root isolation. A proof for n=4 is a partial win.

## Our approach and status

Optimize small-support product laws and certify every endpoint and stationary point of player 1’s payoff curve. For a positive proof, justify any reduction from arbitrary measures. No new bound or counterexample is claimed.

## Sources

- <https://arxiv.org/pdf/2412.19855>
- <https://arxiv.org/pdf/2208.02788>
