# 014 · He–Holmes Conjecture 9 (attributed to Angel–Holmes): a short stack is always worse off than a tied one

**Result.** A computer-assisted proof of **Conjecture 9** of Angel Y. He and Mark Holmes,
*All In: Give me your money!* ([arXiv:2410.15329](https://arxiv.org/abs/2410.15329), Section 5.3), posed by Omer Angel
and Mark Holmes: in the three-player "all in" betting game, for all stacks x, y, z > 0 with x < y,

**f(x, y, z) − f(y, y, z) ≥ 379/1,813,985,280 > 0,**

where f is the probability that player 1 busts first. A player with a shorter stack than an opponent is always strictly
more likely to bust first than if the two were tied, and the proof even gives an explicit margin that holds everywhere.

**Status.** Lowered to PROMISING pending a human expert's sign-off on two analytic lemmas. The maintainer reproduced
every certificate bound: [elder-plinius/V3R1T4S PR #192](https://github.com/elder-plinius/V3R1T4S/pull/192).
It passed the V3R1T4S gauntlet (three independent skeptic agents + honesty gate) and a blind review by a fresh Codex context (this result came from a Codex research lane, so that review is independent but not cross-model).
Not peer reviewed and not formalised in a proof assistant.

---

## The problem

Three players hold real stacks x, y, z. Each round a random pair of players goes all in on a fair coin flip: the bet is
the whole stack of the poorer of the two, so one of them either doubles up or busts. The question is who busts first:
the final-table dynamics of a poker tournament (the setting of ICM) in their simplest form. Angel and Holmes showed a
surprising fact: busting-first probability is **not** monotone in your own stack (you can lower your chance of busting
first by giving chips away). They conjectured two weaker monotonicity statements. He and Holmes proved the first
(starting with more money than an opponent is better, Theorem 1 of their paper) with a computer-assisted proof, and left
the second, "a short stack is always worse off than a stack tied with the opponent's", open after their
finite-depth computation became too slow.

## What we found

The game is scale invariant, and from every state the six possible transitions (which pair plays, who wins the flip)
each have probability 1/6, so the game tree from any region of starting stacks can be followed exactly. The proof
partitions the space of stacks into regions and, on each, bounds the busting-first probabilities by exact backward
recursion over a finite game tree with rational arithmetic, plus a tail bound for the (exponentially rare) games still
running at the cut-off. Three region certificates cover the whole theorem: 9,839 tree nodes and 6,561 leaves, including
every boundary case where two stacks are equal.

**Checks it passed.** The run's own exact verifiers; three skeptic agents in fresh contexts plus the honesty gate and
package checker; and a blind review that re-derived every region bound with separately written C++ backward and forward
recursions and cross-checked sample values against exact absorbing-Markov-chain solutions.

## What it is not

- Not a proof-assistant formalisation (Lean, Coq, Isabelle), not peer reviewed, and the margin 379/1,813,985,280 is a
  certified lower bound, not the exact infimum.
- Nothing about general monotonicity in your own stack (which is false) or about the unit-step gambler's-ruin game.

## Verify it yourself

Submission folder:
[known-knowns/all-in-three-player-ruin-angel-holmes-conjecture/2026-10-15-r-nikhil-4a37999f](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-4a37999f/known-knowns/all-in-three-player-ruin-angel-holmes-conjecture/2026-10-15-r-nikhil-4a37999f)
— run `sh verify-it-yourself/run_checks.sh` there (Python 3 and a C++17 compiler, under a minute); the last line should
be `PASS`.

## Credits

Omer Angel and Mark Holmes (the conjecture); Angel Y. He and Mark Holmes (the paper, Theorem 1 and their MeshItUp
region-partition framework, which inspired the region approach; none of their solver code is used); the V3R1T4S kit by
[elder-plinius](https://github.com/elder-plinius/V3R1T4S).
