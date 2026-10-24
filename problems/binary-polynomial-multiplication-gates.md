# Smaller circuits for binary polynomial multiplication

**Open problem.** How few elementary bit operations can multiply two binary polynomials? For n-term inputs f and g over GF(2), find an AND/XOR circuit computing h_k = ∑_{i+j=k} f_i g_j for every k from 0 to 2n−2, using fewer gates than the best published circuit for some 2 ≤ n ≤ 100.

**Status.** Find and Peralta’s Table 5 reports circuit sizes of 349 for n=16 and 3673 for n=64. These are reference sizes, not a verified complete current frontier. The D’angella et al. and De Piccoli–Visconti–Rizzo comparisons remain incomplete; a record claim remains PENDING TABLE CHECK. [Status source](<http://www.cs.yale.edu/homes/peralta/CircuitStuff/CMT.html>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

GF(2) has two values: addition is XOR and multiplication is AND. For illustration, multiplying f_0 + f_1 x by g_0 + g_1 x gives coefficients f_0g_0, f_0g_1 XOR f_1g_0, and f_1g_1. A circuit may share intermediate values. Here each two-input AND or XOR costs one gate; inputs, reused wires and output labels are free. Constants and other gate types are excluded. This is unreduced polynomial multiplication, before any finite-field reduction.

## Backstory

- 2009-05-31: Bernstein’s table version provided straight-line programs through n = 1000.
- 2015: Cenk and Hasan published later circuit bounds.
- 2019: Find and Peralta compared sizes for 2 ≤ n ≤ 100.
- 2020: De Piccoli, Visconti and Rizzo published another source that the input flags as unread.

## Why it matters

Binary multiplication is a building block for binary-field arithmetic used in authentication, elliptic-curve arithmetic and code-based cryptography. Fewer gates can reduce the size of an implementation, although gate count alone says nothing about its latency or security.

## Real-world uses

Concrete uses include carry-less multiplication and the multiplication stage of GHASH in AES-GCM. A small verified circuit also supplies a reusable component for larger arithmetic circuits.

## How to think about it

One choice determines which products to compute; another determines how cheaply to combine them with XORs. Improving either layer can matter. The proposal suggests sharing linear intermediates, replacing small circuit regions by equivalent cheaper ones, and exploring recursive splits. A fair comparison must recount all reference circuits in the same gate basis.

## What counts as a solution

Provide an explicit straight-line program with the specified inputs, outputs and gate basis, strictly smaller than every applicable reference value for that n, including later literature. Check each output symbolically in the Boolean polynomial ring, where x² = x; sampling is insufficient. Recount available reference programs with the same counter. Until the unread sources are checked, even a correct smaller candidate must retain PENDING TABLE CHECK. Larger n and certified optimality proofs are separately described partial targets in the proposal.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

## Our approach

Search equivalent bilinear formulas and simplify their XOR layers, then verify every output symbolically. Treat the missing reference-table comparison as a required step before any record claim.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://binary.cr.yp.to/m.html>
- <http://www.cs.yale.edu/homes/peralta/CircuitStuff/CMT.html>
- <https://pmc.ncbi.nlm.nih.gov/articles/PMC6774206/>
- <https://link.springer.com/article/10.1007/s13389-019-00210-w> — HTTP 303; not retrieved.

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
