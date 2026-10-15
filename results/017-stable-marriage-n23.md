# 017 · 19,305,568 stable matchings in a 23×23 marriage market

**Result.** An explicit stable-marriage instance with 23 people on each side that has exactly **19,305,568** stable
matchings, against **15,481,956** listed for this size in OEIS [A357271](https://oeis.org/A357271) (Thurber's 2002
compositions): **f(23) ≥ 19,305,568** (+24.7 %). It was found by search, not by composing known instances (23 is prime,
so no product of smaller instances reaches it).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate) and a blind review by a
fresh Codex context (this result came from a Codex research lane, so that review is independent but not cross-model),
and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #195](https://github.com/elder-plinius/V3R1T4S/pull/195).

---

## The problem

The maximum number of stable matchings *f(n)*: see the [problem page](../problems/stable-marriage-max-stable-matchings.md).

## What we found

The pipeline of [012](012-stable-marriage-n13-9836.md): a non-repeating-word construction with an exact evaluator
(19,290,640), refined by multi-move and non-local search to 19,305,568. Counted by independent exact counters, with a
blocking-pair check at every stable matching. The best composition of known instances we could build for n = 23 (the
best n = 22 composition padded with one mutually-first-choice pair) has 12,277,568.

## What it is not

- Not the exact maximum *f(23)*, only a better lower bound.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-94f73e18](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-94f73e18/known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-94f73e18)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

## Credits

As for [012](012-stable-marriage-n13-9836.md).
