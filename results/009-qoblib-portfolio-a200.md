# 009 · A better portfolio for a quantum-optimisation benchmark

**Result.** A feasible ten-period portfolio for the [QOBLIB](https://github.com/ZIB-AOPT/QOBLIB) benchmark instance
`po_a200_t10_s00` (200 assets, 10 periods, budget B = 50, risk aversion λ = 0.01) with exact objective **−644,342**
under the library's reference model — better (lower) than the best value posted for this cell anywhere we could find,
**−401,535** (an open QOBLIB pull request, #87). The official best-known table has no row for this cell yet.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by
a second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #170](https://github.com/elder-plinius/V3R1T4S/pull/170). Also submitted to QOBLIB
itself, together with [011](011-qoblib-portfolio-a200-orig.md), with the AI use disclosed as their policy asks:
[ZIB-AOPT/QOBLIB pull request #92](https://github.com/ZIB-AOPT/QOBLIB/pull/92).

---

## The problem

QOBLIB, the *Quantum Optimization Benchmarking Library* ([arXiv:2504.03832](https://arxiv.org/abs/2504.03832)), collects
hard optimisation problems so that quantum and classical solvers can be compared on equal terms. Class 06 is
multi-period portfolio optimisation: choose integer holdings (long or short) of each asset in each period to balance
expected return against risk (a covariance penalty), paying transaction costs on every rebalance and a cost for short
positions, with a fixed budget. It is the textbook mean-variance trade-off made realistic, and it becomes a hard
integer quadratic programme very quickly: exactly the kind of instance used to test whether new solvers beat old ones.

## What we found

A research lane built an exact evaluator of the reference model and improved step by step, always re-scoring
candidates exactly: a relaxation rounded to integers (−487k), local search (−517k), an exact dynamic programme that
chains the best period-by-period choices across many solutions (−520k), then rounds of per-period local search with
the neighbouring periods fixed, recombined by the same dynamic programme (−618,978 after 6 rounds, −644,342 after 60
more). The best portfolio found scores −644,342 (risk 63,057, return −784,113, transaction costs 76,812,
cash interest −640, short costs 542): about 60 % lower than the best posted value.

**Checks it passed.** Three skeptic agents in fresh contexts plus the honesty gate and package checker; and a blind
cross-review by OpenAI Codex, which first reproduced the values posted in QOBLIB pull requests #87 and #64 and then
evaluated this portfolio with two separately written exact evaluators, finding all ten periods feasible and the same
objective.

## What it is not

- Not a proven optimum, and not a row of the official table (which has no row for this cell).
- One instance and one parameter setting; other cells of the class were not claimed.

## Verify it yourself

Submission folder:
[known-knowns/qoblib-market-split-and-portfolio/2026-10-15-r-nikhil-8650bc1e](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-8650bc1e/known-knowns/qoblib-market-split-and-portfolio/2026-10-15-r-nikhil-8650bc1e)
— run `sh verify-it-yourself/run_checks.sh` there (it downloads the public instance files from a pinned QOBLIB commit);
the last line should be `PASS`.

Solution sha256: `8650bc1e720ff19bd4f17cedefb5b4021dbcd1a3315c8a79abd6d79cf82efe62`.

## Credits

The QOBLIB authors and maintainers (ZIB and partners); the authors of the posted solutions in QOBLIB pull requests #87
and #64; the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
