# 006 · 12,277,568 stable matchings in a 22×22 marriage market

**Result.** An explicit stable-marriage instance with 22 people on each side that has exactly **12,277,568** stable
matchings — more than the best known value for that size (**11,221,136**, OEIS [A357271](https://oeis.org/A357271),
from Edward Thurber's 2002 compositions). So **f(22) ≥ 12,277,568** (+9.4 %).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by a
second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #157](https://github.com/elder-plinius/V3R1T4S/pull/157).

---

## The problem

The maximum number of stable matchings *f(n)* — see the [problem page](../problems/stable-marriage-max-stable-matchings.md).

## What we found

The same doubling as in [002](002-stable-marriage-n18.md) — the lexicographic product of a record instance with Knuth's
2×2 market, which is exactly the classic Irving–Leather doubling — applied to the published 11×11 record instance of
Ong et al. (1,690 stable matchings) gives a 22×22 instance with **12,277,568** stable matchings, beating the table.

**Checks it passed.** Several exact counters in the run; three independent skeptic agents plus the honesty gate and
package checker; and a blind cross-review by OpenAI Codex: two exact counters of its own agreed on the count (and on every
partner frequency) after reproducing the published values at *n* = 7, 9, 11, 13 and 15. (Its first review asked whether
*n* = 22 was within the research charter's stated cells; after a scope note quoting the charter, it passed.)

## What it is not

- Not the exact maximum *f(22)* — only a better lower bound, and a mechanical one: it lifts a known record.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-213b4ac7](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-14-r-nikhil-213b4ac7/known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-213b4ac7)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

Instance sha256: `213b4ac73bfb4218a4295514410d0d53b6a87f48e8f1462d61382579efdd5b37`.

## Credits

Knuth; Irving and Leather; Thurber; Ong, Ang, Ho, Eilers, Marks and Buzi (the 11×11 block); Dan Eilers (OEIS A357269 /
A357271); the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
