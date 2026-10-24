# Certify the exact optimum of a small QOBLIB portfolio instance

**Open problem.** Can the exact global optimum of a010_t10_orig_b004_l1e-03 be certified?

**Status.** Thorsten Koch and colleagues’ Quantum Optimization Benchmarking Library publishes a multi-period Markowitz benchmark with transaction costs, cash interest and short positions. On 2026-10-24 the portfolio table labels a010_t10_orig_b004_l1e-03 best known with incumbent -8397. Maximilian Schicker’s 2025-08-19 submission reports -8397 and numerical bound -15342.65126758 after 3600.03 seconds; that bound is not an exact proof. The canonical schedule file repeats instance po_a010_t10_orig, budget 4, lambda 0.001 and objective -8397. Fix the shipped rounded integer-coefficient BQP, dataset po_a010_t10_orig, a=10, t=10, B=4 and lambda=1/1000; keep the other parameter_u3_c10.zpl settings, including unit=100000, cash=1000000, ub=3, delta=0.001, nu=0.0001, rho=0.000025 and upscale=1. There are three interchangeable copies per asset, direction and period, plus four-bit cash and seven-bit budget slack registers. The exact global optimum remains unproved in the source table.

Status checked: 2026-10-24 (live best-known status, submission gap, canonical schedule header and model definitions confirmed). [Status source](<https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/solutions/README.md>).

## The problem

The instance has ten assets, ten periods and a budget of four long or short units. It combines risk, returns, transaction costs, cash interest and short-position costs. The target is the shipped rounded integer BQP.

## Backstory

The live table lists incumbent -8397 as best known. Schicker’s 2025 submission reports the same objective and a numerical bound -15342.65126758. This gap is evidence of unfinished optimization, not a certified lower bound.

## Why it matters

A matching exact lower bound would distinguish a global optimum from a heuristic incumbent. A candidate with the same objective can be a full win when its global optimality is certified.

## Real-world uses

This benchmark tests methods for multi-period allocation. Its rounded objective and artificial unit budget make it an optimization test, not investment advice.

## How to think about it

The three unit copies are interchangeable. Canonical count states reduce a period to 20 counts in 0..3 with total at most four, giving 10606 states. The checker describes why aligned copy slots preserve the optimum. Boundary costs and rounding positions must follow the shipped model.

## What counts as a solution

Give a globally optimal feasible position schedule for this exact instance, its integer objective v <= -8397, and an independently checkable matching lower-bound certificate. A solution equal to -8397 is a full win only with an exact global optimality certificate. Certificates may be a complete dynamic-programming/Bellman certificate or an exact rational branch-and-bound proof for the published BQP; a solver status or floating-point gap alone does not qualify.

Read the original price and covariance decimal strings as rationals. Reproduce the coefficients of bqp_u3_c10.zpl using Zimpl round-half-away-from-zero, at the same places as the model. Check every unit count is an integer in 0..3, per-period total count <=4, cash slack 10-net in 0..15 and budget slack 4-total in 0..127. Reconstruct canonical copy slots, slack bits and the complete objective, including initial purchases, final liquidation and the model's actual indexing/multiplicities. Cross-check with the public exact Rust checker. For optimality, enumerate per-period count states and verify all Bellman lower-bound inequalities and a matching attaining path. There are 10606 count states before any additional pruning: 20 direction/asset counts in 0..3 with total <=4. Direct comparisons are about a billion small integer operations; a certified weighted-L1 distance transform can reduce this substantially. A verifier should take minutes to hours in compiled code.

## Our approach

Build an exact dynamic program and certify its Bellman inequalities plus an attaining path. A strictly better feasible integer objective is an enumerated partial win. The preparation confirms source metadata and claims no new optimum.

New candidate certificates use the bank’s commit-only disclosure rule. This preparation submits nothing.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/solutions/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/submissions/20250819_MIP_Schicker/po_a010_t10_orig/po_a010_t10_orig_b004_l1e-3/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/solutions/po_a010_t10_orig/po_a010_t10_orig_b004_l1e-3.bst.sol>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/models/binary_quadratic_programming/bqp_u3_c10.zpl>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/models/binary_quadratic_programming/parameter_u3_c10.zpl>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/06-portfolio/check/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/README.md>
