# 016 · 5,400,616 stable matchings in a 21×21 marriage market

**Result.** An explicit stable-marriage instance with 21 people on each side that has exactly **5,400,616** stable
matchings, against **3,506,880** listed for this size in OEIS [A357271](https://oeis.org/A357271) (Thurber's 2002
compositions): **f(21) ≥ 5,400,616** (+54 %).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate) and a blind review by a
fresh Codex context (this result came from a Codex research lane, so that review is independent but not cross-model).
The maintainer independently confirmed the result. Small README fixes were requested and done on 2026-10-24.
Merge expected: [elder-plinius/V3R1T4S PR #194](https://github.com/elder-plinius/V3R1T4S/pull/194).

---

## The problem

The maximum number of stable matchings *f(n)*: see the [problem page](../problems/stable-marriage-max-stable-matchings.md).

## What we found

The pipeline of [012](012-stable-marriage-n13-9836.md) and [013](013-stable-marriage-n19.md): a non-repeating-word
construction with an exact evaluator gave a 21×21 instance with 4,699,360 stable matchings, a multi-move search reached
5,382,608, and a further search with non-local moves reached 5,400,616. Counted by independent exact counters, with a
blocking-pair check at every stable matching.

## What it is not

- Not the exact maximum *f(21)*, only a better lower bound.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-7954ceb4](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-7954ceb4/known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-7954ceb4)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

## Credits

As for [012](012-stable-marriage-n13-9836.md).
