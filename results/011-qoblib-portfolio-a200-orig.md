# 011 · A better portfolio for a second quantum-optimisation benchmark instance

**Result.** A feasible ten-period portfolio for the [QOBLIB](https://github.com/ZIB-AOPT/QOBLIB) benchmark instance
`po_a200_t10_orig` (200 assets, 10 periods, budget B = 50, risk aversion λ = 0.01) with exact objective **−691,624**
under the library's reference model, against a best posted value of **−551,385** (open QOBLIB pull request #87), about
25 % lower. The official best-known table has no row for this cell yet. This is the sibling of
[009](009-qoblib-portfolio-a200.md) and was found first, by the same pipeline.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by
a second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #176](https://github.com/elder-plinius/V3R1T4S/pull/176). Also submitted to QOBLIB itself, together with
[009](009-qoblib-portfolio-a200.md), with the AI use disclosed as their policy asks:
[ZIB-AOPT/QOBLIB pull request #92](https://github.com/ZIB-AOPT/QOBLIB/pull/92).

---

## The problem

Multi-period portfolio optimisation from QOBLIB class 06: see [009](009-qoblib-portfolio-a200.md) for what the benchmark
is and why it is hard.

## What we found

The key observation: every period's covariance matrix is a 30-day sample covariance of rank 29, so integer baskets
whose 29-factor exposure nearly cancels carry almost no risk; the problem behaves more like a closest-vector problem than
a generic quadratic one. A continuous relaxation on the 29 factors showed large headroom (about −836k). Rounding it and
descending exactly gave −552k to −565k, iterated local search −596k, and an exact dynamic programme that mixes periods
from different solutions (good portfolios re-trade about 90 % of their units every period, so periods nearly decouple)
pushed it to −691,624 (risk 58,939, return −825,237, transaction costs 75,179).

**Checks it passed.** Three skeptic agents in fresh contexts plus the honesty gate and package checker; and a blind
cross-review by OpenAI Codex, which reproduced the values posted in QOBLIB pull requests #87 and #64 for this cell and
then evaluated this portfolio with two separately written exact evaluators, finding all ten periods feasible and the
same objective.

## What it is not

- Not a proven optimum, and not a row of the official table (which has no row for this cell).

## Verify it yourself

Submission folder:
[known-knowns/qoblib-market-split-and-portfolio/2026-10-14-r-nikhil-3066ef03](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-14-r-nikhil-3066ef03/known-knowns/qoblib-market-split-and-portfolio/2026-10-14-r-nikhil-3066ef03)
— run `sh verify-it-yourself/run_checks.sh` there (it downloads the public instance files from a pinned QOBLIB commit);
the last line should be `PASS`.

## Credits

The QOBLIB authors and maintainers; the authors of the posted solutions in QOBLIB pull requests #87 and #64; the
V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
