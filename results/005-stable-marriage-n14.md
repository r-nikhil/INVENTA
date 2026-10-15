# 005 · 24,992 stable matchings in a 14×14 marriage market

**Result.** An explicit stable-marriage instance with 14 people on each side that has exactly **24,992** stable
matchings — more than the best known value for that size (**20,176**, OEIS [A357271](https://oeis.org/A357271), from
Edward Thurber's 2002 compositions). So **f(14) ≥ 24,992** (+23.9 %).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by a
second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #156](https://github.com/elder-plinius/V3R1T4S/pull/156).

---

## The problem

The maximum number of stable matchings *f(n)* in a market of *n* men and *n* women — see the
[problem page](../problems/stable-marriage-max-stable-matchings.md) and [discovery 001](001-stable-marriage-n15.md).

## What we found

The size-14 cell had not been touched by the recent computer searches; its table value still came from Thurber's 2002
compositions. A research lane tried building it from two copies of a 7×7 record block: plain two-copy gluings gave
2 × 85² = 14,450. The *lexicographic product* — the 7×7 block as the outer structure and Knuth's 2×2 market inside
(each person becomes a couple; men rank by the outer ranking, then by their inner list; women likewise with the inner
order reversed), the same doubling as in [002](002-stable-marriage-n18.md) — gave **24,992**. The 7×7 block is the
instance with 85 stable matchings from Myunglae Jo's 2026 computer-assisted study of *n* = 7.

**Checks it passed.** Several exact counters in the run; three independent skeptic agents plus the honesty gate and
package checker; and a blind cross-review by OpenAI Codex with two counters of its own, after reproducing the published
values at *n* = 7, 9, 11, 13 and 15. (The review first failed because our claim text cited the wrong OEIS file for the
20,176 bar — the panel's own skeptics had flagged the same slip. After the citation was corrected, it passed. The
numbers never changed.)

## What it is not

- Not the exact maximum *f(14)* — only a better lower bound.
- The building block's own maximality (*f*(7) = 85) is a recent claim not yet peer reviewed; this result does not depend
  on it, because the 14×14 instance is counted directly.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-2eeddab2](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-14-r-nikhil-2eeddab2/known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-2eeddab2)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

Instance sha256: `2eeddab210507ca8fecf7cb18e88a27245dd861ab7497acfc0d023766cf76965`.

## Credits

Knuth; Irving and Leather; Thurber; Myunglae Jo (the 7×7 block with 85 stable matchings); Ong, Ang, Ho, Eilers, Marks
and Buzi; Dan Eilers (OEIS A357269 / A357271); the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
