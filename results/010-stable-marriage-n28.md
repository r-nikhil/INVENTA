# 010 · 2,497,797,760 stable matchings in a 28×28 marriage market

> **Update (2026-10-15): closed by the V3R1T4S maintainer, not listed as a record.** The count is exactly right, but
> the instance is a mechanical composition (doubling) of known instances with no search. It beats the OEIS A357271
> data line only because that line is stale: its odd terms predate the Ong et al. instance file and its even terms
> predate doubling those instances. The best composition of known instances is the real bar. Closed PR: [#174](https://github.com/elder-plinius/V3R1T4S/pull/174).

**Result.** An explicit stable-marriage instance with 28 people on each side that has exactly **2,497,797,760** stable
matchings. That beats the value listed for this size in OEIS [A357271](https://oeis.org/A357271) (**2,000,043,808**,
from Edward Thurber's 2002 compositions; +24.9 %) and also the **2,369,365,120** you get by applying the same doubling
twice to the best published 7×7 instance (+5.4 %). So **f(28) ≥ 2,497,797,760**.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by a
second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #174](https://github.com/elder-plinius/V3R1T4S/pull/174).

---

## The problem

The maximum number of stable matchings *f(n)* — see the [problem page](../problems/stable-marriage-max-stable-matchings.md).

## What we found

Doubling a market (the lexicographic product with Knuth's 2×2 market, the classic Irving–Leather construction) roughly
squares the number of stable matchings, so the best way to reach large sizes is to double the best small blocks. Our
14×14 record ([005](005-stable-marriage-n14.md), 24,992) is itself the doubling of Myunglae Jo's 7×7 instance with 85
stable matchings; doubling it once more gives this 28×28 instance. Counting 2.5 billion stable matchings needs the
rotation-poset structure: the count is the number of closed subsets of the instance's rotation poset, computed by a
memoised dynamic programme and confirmed by a full enumeration that re-checks every matching against the definition.

**Checks it passed.** Three agreeing exact counters in the run; three skeptic agents plus the honesty gate and package
checker; and a blind cross-review by OpenAI Codex: two exact counters of its own reproduced the published values at
*n* = 7, 9, 11, 13 and 15, rebuilt the 2,369,365,120 baseline from the published 7×7 instance, and counted this instance.
(Its first two reviews asked for the comparison to be stated more precisely; the claim now names both baselines.)

## What it is not

- Not the exact maximum *f(28)*, only a better lower bound, and a mechanical one: it doubles a known record twice.
- It relies on Jo's 7×7 instance (a 2026 preprint); the instance itself is checked directly, so the count does not
  depend on that preprint's optimality proof.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-dbf2d891](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-14-r-nikhil-dbf2d891/known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-dbf2d891)
— run `sh verify-it-yourself/run_checks.sh` there (about 10 seconds and 2 GB of memory; needs a C compiler); the last
line should be `PASS`.

Instance sha256: `dbf2d89155213b672ef7514493d16c7f02225a84dbcc31f4ae30068f085e1ad0`.

## Credits

Knuth; Irving and Leather; Thurber; Myunglae Jo (the 7×7 block); Ong, Ang, Ho, Eilers, Marks and Buzi (the published
7×7 to 15×15 records); Dan Eilers (OEIS A357269 / A357271); the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
