# Higher unrestricted Boolean nonlinearity in odd dimensions

**Open problem.** Can an unrestricted Boolean function in 9, 11 or 13 variables beat the applicable nonlinearity bar?

**Status.** Claude Carlet, Marko Ðurasevic, Domagoj Jakobovic, Stjepan Picek and Luca Mariot, A Systematic Study on the Design of Odd-Sized Highly Nonlinear Boolean Functions via Evolutionary Algorithms (arXiv:2504.17666v1, April 2025; journal publication December 2025), describe maximum nonlinearity for odd n>7 as open. Table 1 gives unrestricted best-known values 242,996,4040 for n=9,11,13, and upper bounds 244,1000,4050. Nonlinearity is minimum Hamming distance to an affine Boolean function. The n=9 construction is credited to Kavut and Yücel. Direct sums of an n=9, nonlinearity-242 function with two- or four-variable bent functions already give 996 and 4040. These compositions belong to the bar. Author spellings here follow the cited preprint.

Status checked: 2026-10-15 (supplied literature-status date; primary publication re-read 2026-10-24, later literature not independently rechecked). [Status source](<https://arxiv.org/html/2504.17666v1>).

## The problem

Nonlinearity is the minimum Hamming distance from a Boolean function to any affine Boolean function. The target has no balancedness, algebraic-degree or symmetry restriction.

## Backstory

The 2025 preprint’s Table 1 gives 242,996,4040 for nine, eleven and thirteen variables. Its upper bounds are 244,1000,4050. The larger recorded constructions can already be obtained by composing a nine-variable record with bent functions.

## Why it matters

The numerical plateaus reflect a hard search despite cheap exact verification. A construction above the applicable bar narrows a finite gap.

## Real-world uses

High nonlinearity is one design criterion for cryptographic Boolean components. A whole cryptosystem also depends on other properties.

## How to think about it

Walsh spectra turn the objective into minimizing the largest absolute transform coefficient. Direct sums multiply Walsh spectra. Combining the known n=9 function with two- or four-variable bent functions already gives 996 or 4040, so those compositions are not improvements.

## What counts as a solution

Supply the complete truth table of f:{0,1}^n→{0,1}, for n=9,11 or 13, with nonlinearity strictly greater than 242,996 or4040 respectively. No balancedness, rotation symmetry or algebraic-degree restriction is imposed. Report the full Walsh spectrum and the exact achieved nonlinearity; the checker recomputes it. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar.

Validate 2^n Boolean table entries in explicitly specified lexicographic bit order. Apply the integer fast Walsh–Hadamard transform to (-1)^f(x). Compute NL(f)=2^(n−1)−max_a |W_f(a)|/2, which includes distances to both affine constants. Check Parseval sum_a W_f(a)^2=2^(2n) and compare the exact integer result with the threshold. This requires at most 8192×13 additions and no floating-point tolerance.

## Our approach

Search symmetry-restricted families or local truth-table changes, then expand and check the unrestricted table with an integer Walsh transform. No higher value is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://arxiv.org/html/2504.17666v1>
- <https://link.springer.com/article/10.1007/s10710-025-09526-5>
