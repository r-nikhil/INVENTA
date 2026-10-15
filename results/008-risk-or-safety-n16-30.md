# 008 · Exact optimal-play odds in "Risk or Safety" for 16 to 30 points

**Result.** The exact probability that the first player wins the coin push-your-luck race *Risk or Safety* under
optimal play by both sides, as a reduced fraction, for every target from **n = 16 to n = 30** points: fifteen new
terms of OEIS [A387261](https://oeis.org/A387261)/[A387262](https://oeis.org/A387262), which until now stopped at
n = 15. Each value comes with a certificate: the win probability and the optimal action (toss or stop) at every
position of the game, which anyone can check in exact arithmetic in about 30 seconds. At n = 30 the fraction has a
152-digit numerator and denominator.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by
a second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #169](https://github.com/elder-plinius/V3R1T4S/pull/169).

---

## The problem

Two players race to *n* points. On your turn you toss a fair coin as often as you like: heads adds an open point,
tails wipes out the points you have not banked and ends your turn. You may stop at any time and bank your open points;
reaching *n* wins. It is the purest form of a push-your-luck decision (Pig, Can't Stop, blackjack's "hit or stand"):
every toss trades the risk of losing what you have against the chance of getting ahead. The game and its first 15 exact
values come from [arXiv:2603.01002](https://arxiv.org/abs/2603.01002); the optimal strategies are OEIS
[A394776](https://oeis.org/A394776).

## What we found

The optimal win probabilities satisfy a system of Bellman equations over all positions (open points, your bank, the
opponent's bank), which is solved exactly with rational arithmetic, position by position. A research lane wrote the
solver, reproduced all 15 published terms and all 400 published optimal toss counts, and then solved n = 16 to 30.
Every value is backed by its full table of positions and actions, so nobody has to trust the solver: the checker only
verifies that each position's value equals the better of its two actions.

**Checks it passed.** The run's own exact verifiers; three skeptic agents in fresh contexts plus the honesty gate and
package checker; and a blind cross-review by OpenAI Codex, which reproduced the 15 published terms first and then
verified all 112,840 positions of the 30 certificates with two exact methods that share no logic.

## What it is not

- Nothing beyond n = 30 is claimed here (the lane computed further; those values are not yet reviewed).
- No published value is corrected: all earlier terms are reproduced exactly.

## Verify it yourself

Submission folder:
[known-knowns/risk-or-safety-exact-optimal-play/2026-10-15-r-nikhil-8e69676d](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-8e69676d/known-knowns/risk-or-safety-exact-optimal-play/2026-10-15-r-nikhil-8e69676d)
— run `sh verify-it-yourself/run_checks.sh` there (Python 3 standard library and gzip); the last line should be `PASS`.

Values table sha256: `8e69676d99d3dc6726098a75c1167f2820f2c3e9c2bd0b82ed98e2dbb8446f24`.

## Credits

The authors of arXiv:2603.01002 (the game, its equations and the first 15 terms); the OEIS contributors of A387261,
A387262 and A394776; the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
