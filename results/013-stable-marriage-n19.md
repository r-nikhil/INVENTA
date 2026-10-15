# 013 · 935,662 stable matchings in a 19×19 marriage market

**Result.** An explicit stable-marriage instance with 19 people on each side that has exactly **935,662** stable
matchings, against **637,336** listed for this size in OEIS [A357271](https://oeis.org/A357271) (Thurber's 2002
compositions): **f(19) ≥ 935,662** (+46.8 %). Odd sizes like 19 cannot be reached by simply doubling a smaller record.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate) and a blind review by a fresh Codex context (this result came from a Codex research lane, so that review is independent but not cross-model), and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #191](https://github.com/elder-plinius/V3R1T4S/pull/191).

---

## The problem

The maximum number of stable matchings *f(n)*: see the [problem page](../problems/stable-marriage-max-stable-matchings.md).

## What we found

The same pipeline as [012](012-stable-marriage-n13-9836.md): a non-repeating-word construction with an exact evaluator
gave an n = 19 instance with 896,068 stable matchings, and a multi-move search improved it to 935,662. Counted by
independent exact counters, with a blocking-pair check at every stable matching.

## What it is not

- Not the exact maximum *f(19)*, only a better lower bound.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-1e284a0d](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-1e284a0d/known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-1e284a0d)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

## Credits

As for [012](012-stable-marriage-n13-9836.md).
