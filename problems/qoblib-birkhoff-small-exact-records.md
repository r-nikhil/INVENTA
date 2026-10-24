# Smaller exact Birkhoff decompositions for two QOBLIB matrices

**Open problem.** Can B5_25_2 or B6_36_10 have a smaller exact Birkhoff decomposition?

**Status.** QOBLIB’s Minimum Birkhoff Decomposition problem minimizes the number of permutation matrices in an exact convex decomposition of a doubly stochastic matrix. On 2026-10-24 its table lists B5_25_2 at 14 and B6_36_10 at 20, both best known. The source credits J. Kulkarni, E. Lee and M. Singh (2017), and F. Dufossé and B. Uçar (2016). Maximilian Schicker’s submissions dated 2026-01-10 give integer-weight-model numerical lower bounds 13 and 11, not exact unrestricted lower bounds. Both target matrices have scale 10000 in qbench_05_dense.json and qbench_06_dense.json. Independent exact arithmetic confirms the 14/20-term MIP witnesses. The current .bst.json files have 13/17 terms, but neither support can reconstruct its target over rational weights, in either orientation. Their approximate counts therefore do not settle these exact targets.

Status checked: 2026-10-24 (live table, exact incumbent witnesses and inconsistent approximate supports independently checked). [Status source](<https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/solutions/README.md>).

## The problem

A doubly stochastic matrix specifies fractional assignments. A Birkhoff decomposition realizes it as a lottery over permutation assignments. The objective is the number of distinct assignments with positive weights. The shipped integer matrices have row and column sum 10000.

## Backstory

The live table lists exact incumbents of 14 and 20 terms. Schicker’s January 2026 MIP files reconstruct both targets exactly. Smaller current .bst files use 13 and 17 terms, but exact elimination shows their supports inconsistent with the target equations in either orientation.

## Why it matters

Exact equality separates an assignment lottery with the prescribed marginals from an approximation. A solver’s integer-weight lower bound does not settle the optimum with unrestricted weights.

## Real-world uses

These decompositions model randomized assignments and schedules. A smaller lottery can reduce the number of distinct schedules needed to implement fractional allocations.

## How to think about it

There are only 120 or 720 permutation columns. Choose a small support, then solve its weight equations exactly. Approximate supports may guide search, but their existing inconsistent equations cannot be repaired by more numerical precision.

## What counts as a solution

For either named matrix A, give pairwise distinct permutations and strictly positive rational weights w_k summing to 10000 such that A=sum_k w_k P_k entrywise exactly, with at most 13 terms for B5_25_2 or at most 19 for B6_36_10. This is a record win; global minimality need not be proved. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar. Alternatively, close either exact optimum by an attaining decomposition and an independently checkable lower-bound certificate valid for arbitrary nonnegative real weights. A certificate restricted to integer weights does not establish the latter claim.

Locate instances by their id, not JSON insertion order. Check integer matrix entries, common row/column sum 10000 and each submitted permutation of 1..n. Merge duplicate permutations and discard zero weights before counting. Clear rational denominators and check all 25 or 36 reconstruction equations and the weight sum with arbitrary-precision integers; tolerance must be zero. Use row-major storage, as confirmed against the exact MIP incumbents. For an optimality claim, a rational MILP branch proof over all n! support indicators and continuous weights can be checked node by node using Farkas/dual certificates. The small audit script checks fixed supports, not optimality, and is not a substitute for a general lower-bound proof.

## Our approach

Use support-selection optimization and exact local exchanges. Independently clear denominators and check every matrix entry. The preparation verifies published baselines and claims no smaller decomposition.

New candidate certificates use the bank’s commit-only disclosure rule. This preparation submits nothing.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/solutions/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/instances/qbench_05_dense.json>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/instances/qbench_06_dense.json>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/submissions/20260111_MIP_Schicker/B5_25_2/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/submissions/20260111_MIP_Schicker/B6_36_10/README.md>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/submissions/20260111_MIP_Schicker/B5_25_2/B5_25_2_solution.json>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/submissions/20260111_MIP_Schicker/B6_36_10/B6_36_10_solution.json>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/solutions/B5_25_2.bst.json>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/solutions/B6_36_10.bst.json>
- <https://raw.githubusercontent.com/ZIB-AOPT/QOBLIB/main/03-birkhoff/check/README.md>
