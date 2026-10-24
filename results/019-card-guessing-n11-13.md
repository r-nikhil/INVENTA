# 019 · Exact optimal scores in card guessing with yes/no feedback, two-copy decks of 11, 12 and 13 labels

**Result.** The exact maximum expected number of correct guesses, P⁺₂,ₙ, when guessing through a shuffled deck holding two
copies of each of n labels, told only "right" or "wrong" after each guess, for **n = 11, 12, 13**, as reduced fractions
(n = 11: 137912544707079557/45735706696680000 ≈ 3.015424; n = 12 ≈ 3.013730; n = 13 ≈ 3.011617), each with a certificate
that lists the value of every reachable state. Published values stopped at n = 10 (Diaconis, Graham and Spiro, 2022).

**Status.** Confirmed by the V3R1T4S gauntlet as a partial win (three independent skeptic agents + honesty gate).
The maintainer independently confirmed the result. Small README fixes were requested and done on 2026-10-24.
Merge expected: [elder-plinius/V3R1T4S PR #200](https://github.com/elder-plinius/V3R1T4S/pull/200).
The blind cross-model review by OpenAI Codex verified all 37,295,049 certificate states and every value for n = 2–16, but
failed the claim on one clause of the success rule, which asks to reproduce the 2022 table for n = 2–10 to four decimals.
That table cannot be matched by exact values under any single convention: rounding misses n = 7 and truncation misses
n = 10, although every entry is within 0.0001. The PR says so.

---

## The problem

Card guessing with feedback is the mathematics of card counting in its purest form: what is the best you can do when
each answer tells you a little about what is left? With one copy of each card the answer has been known since 1981
(Diaconis and Graham). With two or more copies the optimal strategy is not greedy and has no closed form, so values have
to be computed exactly, and the state space grows fast.

## What we found

A Bellman recursion (Luo's, arXiv:2609.25062, Appendix A) solved exactly in rational arithmetic over canonical states
(two-copy decks are symmetric under relabelling), with a certificate per n: the table of values over every reachable
state, checked state by state by separately written verifiers. Values for n = 14–16 were also computed and passed the
review's certificate check, but are not part of this claim.

## Verify it yourself

Submission folder:
[known-knowns/card-guessing-yes-no-feedback-exact/2026-10-15-r-nikhil-c6c093c2](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-c6c093c2/known-knowns/card-guessing-yes-no-feedback-exact/2026-10-15-r-nikhil-c6c093c2)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

## Credits

Persi Diaconis and Ron Graham (the problem, 1981); Persi Diaconis, Ron Graham and Sam Spiro (*Guessing about guessing*,
2022, the n ≤ 10 table); Luo (arXiv:2609.25062, the recursion); the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
