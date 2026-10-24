# Can rotating a permutation always win Penney’s game?

**Open problem.** Does right rotation always beat a chosen permutation?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2404.06585>).

## The problem

Alice chooses a permutation sigma of length k. Bob moves its last entry to the front to obtain tau. Does tau appear first with probability greater than one half for every k>=3?

## Backstory

Sergi Elizalde and Yixin Lin’s Penney’s game for permutations states this as Conjecture 6.1. The retrieved July 2026 revision proves k=3 and gives truncated numerical evidence for k=4 and k=5. The binary-word game has different results.

## Why it matters

A universal winning response would reveal a structural advantage in overlapping random patterns. It need not be the best possible response.

## Real-world uses

Exact pattern-race probabilities can test tools for time-series patterns, overlapping events and probabilistic combinatorics.

## How to think about it

Generate independent draws from a continuous distribution and read each consecutive window by relative order. The uniform next-rank Markov model is a different experiment. Overlapping-window conditioning matters, and some probabilities in the paper are irrational.

## What counts as a solution

Prove the strict inequality for all k, or certify a permutation whose rotation leaves Alice probability at least one half. Equality also refutes the conjecture but needs an exact proof. Rigorous complete verifications of k=4 or k=5 are partial wins.

## Our approach and status

Count finite order types exactly and retain an explicit tail interval. For horizon H, counts A for Alice wins and R for no winner bound her probability between A/H! and (A+R)/H!. No additional small-k verification or counterexample is claimed.

## Sources

- <https://arxiv.org/pdf/2404.06585>
- <https://doi.org/10.46298/dmtcs.16361>
