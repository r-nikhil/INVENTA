# 015 · A better portfolio for a 400-asset quantum-optimisation benchmark instance

**Result.** A feasible ten-period portfolio for the [QOBLIB](https://github.com/ZIB-AOPT/QOBLIB) benchmark instance
`po_a400_t10_s00` (400 assets, 10 periods, budget B = 100, risk aversion λ = 0.01) with exact objective
**−1,696,664** under the library's reference model, against a best public value of **−1,090,282** (open QOBLIB pull
request #87). The official best-known table has no row for this cell yet.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate) and a blind review by a fresh Codex context (this result came from a Codex research lane, so that review is independent but not cross-model), and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #193](https://github.com/elder-plinius/V3R1T4S/pull/193). Not yet submitted to QOBLIB
itself.

---

## The problem

Multi-period portfolio optimisation from QOBLIB class 06: see [009](009-qoblib-portfolio-a200.md). This instance is
twice as wide (400 assets) as 009 and 011.

## What it is not

- Not a proven optimum, and not a row of the official table (which has no row for this cell).

## Verify it yourself

Submission folder:
[known-knowns/qoblib-market-split-and-portfolio/2026-10-15-r-nikhil-7bf097a5](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-7bf097a5/known-knowns/qoblib-market-split-and-portfolio/2026-10-15-r-nikhil-7bf097a5)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

## Credits

The QOBLIB authors and maintainers; the authors of QOBLIB pull request #87; the V3R1T4S kit by
[elder-plinius](https://github.com/elder-plinius/V3R1T4S).
