# 012 · 9,836 stable matchings in a 13×13 marriage market

**Result.** An explicit stable-marriage instance with 13 people on each side that has exactly **9,836** stable
matchings, far above the best published value for this size, **7,123** (the Ong et al. instance in OEIS
[A357271](https://oeis.org/A357271)'s file), and above our own earlier 7,698 ([003](003-stable-marriage-n13.md)). So
**f(13) ≥ 9,836** (+38 % over the published record).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate) and a blind review by a fresh Codex context (this result came from a Codex research lane, so that review is independent but not cross-model).
The maintainer independently confirmed the result. Small README fixes were requested and done on 2026-10-24, and on
2026-10-25 the maintainer re-confirmed the updated PR (the instance file is unchanged) and will merge after checking the OEIS entry.
Merge expected: [elder-plinius/V3R1T4S PR #190](https://github.com/elder-plinius/V3R1T4S/pull/190) (it supersedes our #150).

---

## The problem

The maximum number of stable matchings *f(n)*: see the [problem page](../problems/stable-marriage-max-stable-matchings.md).

## What we found

A different construction from the local search behind 003: one research lane encoded preference profiles as
non-repeating words and built an exact evaluator for them, reaching 9,796 at n = 13; a second lane ran a new multi-move
search from there and reached 9,836. Both counts were checked by independent exact counters (a rotation-poset counter and
a direct arc-consistency counter, with a blocking-pair check at every stable matching).

## What it is not

- Not the exact maximum *f(13)*, only a better lower bound.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-30437fed](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-30437fed/known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-30437fed)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

Instance sha256: `30437fed4d5de6bf272631b49ae7a94298a2fdefb65c3cd5529df582506c9c56`.

## Credits

Knuth; Irving and Leather; Gusfield and Irving; Thurber; Ong, Ang, Ho, Eilers, Marks and Buzi; Dan Eilers (OEIS); the
V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
