# 018 · Three-player von Neumann poker: the conjectured strategy is a Nash equilibrium for every bet size

**Result.** A proof that in three-player von Neumann poker, as defined by Krityakierne, Thanatipanonda and Zeilberger
([arXiv:2407.16155](https://arxiv.org/abs/2407.16155), Section 4), the threshold strategies they found are a Nash
equilibrium **for every bet size b > 0**: player I bets with the weakest hands (a bluff, x < A) and the strongest
(a value bet, x > B) and checks in between; players II and III each call with any hand y ≥ C. For each b the equations
for A, B, C have exactly one ordered solution 0 < A < C < B < 1, and no player can gain by any deviation, randomised or
not.

**Status.** Confirmed by the V3R1T4S gauntlet as a partial win (three independent skeptic agents + honesty gate),
cross-checked blind by a second model family (OpenAI Codex).
The maintainer reproduced it to 60 digits. A game theorist is being asked to confirm:
[elder-plinius/V3R1T4S PR #196](https://github.com/elder-plinius/V3R1T4S/pull/196).

---

## The problem

Von Neumann's poker model (1944) is the continuous toy game behind modern bluffing theory: hands are real numbers drawn
uniformly from [0, 1], one player may bet, the other may call. Its solution explains why optimal play bluffs with the
*worst* hands, not mediocre ones. The three-player version is much harder, and Krityakierne, Thanatipanonda and
Zeilberger (2024) found the natural threshold strategies by computation and conjectured that they form an equilibrium.
Multiway pots are where real poker strategy gets hard, and exact equilibria of even the simplest multiway models are
rare.

## What we found

The proof works for all bet sizes at once. A continuity and monotonicity argument gives exactly one ordered solution of
the paper's equations for every b > 0. Exact factorisations of each player's payoff differences then show that every
prescribed action is a best response at every hand value, and integration extends this to all measurable, randomised,
unilateral deviations. At b = 2 the proof's exact equilibrium value is 0.1225570747148686…, which agrees with the
paper's printed 0.122557074714865 to 14 decimals; the last printed digit looks like floating-point error.

## What it is not

- The game is the paper's simultaneous version: players II and III decide without seeing each other's choice. If III
  sees II's decision first it is a different game, and the claim says nothing about it.
- Not a claim that this is the only equilibrium; only that this threshold profile is one, for every b.
- A partial win in the bank's terms: the bank entry's full criterion also asks to match the paper's printed b = 2
  digits exactly, which no exact value can do.

## Verify it yourself

Submission folder:
[known-knowns/three-player-von-neumann-poker-equilibrium/2026-10-15-r-nikhil-a40ec86a](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-a40ec86a/known-knowns/three-player-von-neumann-poker-equilibrium/2026-10-15-r-nikhil-a40ec86a)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

## Credits

Tipaluck Krityakierne, Thotsaporn "Aek" Thanatipanonda and Doron Zeilberger (the three-player model and the conjecture); John von
Neumann and Oskar Morgenstern (the original model); the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
