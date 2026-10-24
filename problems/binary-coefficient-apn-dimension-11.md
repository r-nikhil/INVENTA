# A seventh binary-coefficient APN class in dimension eleven

**Open problem.** Can a binary-coefficient quadratic APN function in dimension 11 refute the six-class conjecture?

**Status.** Yuyin Yu, Jingchen Li, Nadiia Ichanska and Nikolay Kaleyski, Classification of quadratic APN functions with coefficients in F2 in dimension 10 (December 2025), classify dimension 10 and conjecture six CCZ-equivalence classes in dimension 11. Table 3 lists x^3, x^5, x^9, x^17, x^33 and x^3+Tr(x^9), with absolute trace GF(2^11) to GF(2). The class is F(x)=sum_{0<=i<j<11} c_ij x^(2^i+2^j), with c_ij in {0,1}. APN means each nonzero input difference has at most two preimages for any output difference. Their partial search found 29 APN functions in six invariant signatures; equivalence within a signature was not fully checked in dimension 11. The estimated full search takes at least 70 single-core years. This target asks for a certified counterexample, not a full classification.

Status checked: 2026-10-15 (supplied literature-status date; primary publication re-read 2026-10-24, later literature not independently rechecked). [Status source](<https://link.springer.com/article/10.1007/s00200-025-00711-8>).

## The problem

An APN function makes every nonzero input difference produce any particular output difference at most twice. Here its polynomial is quadratic and all coefficients lie in {0,1}, although inputs and outputs lie in GF(2^11). The issue is whether every such function is CCZ-equivalent to one of six known representatives.

## Backstory

The December 2025 paper completes dimension ten. Its partial dimension-eleven search finds six invariant signatures but does not prove that they exhaust the class. The six listed representatives and the authors’ warning about within-signature equivalence are both explicit.

## Why it matters

A certified extra class would test a precise classification conjecture. A new truth table within a known class would not do that.

## Real-world uses

APN functions are studied as nonlinear components resistant to differential cryptanalysis. A new class supplies mathematical design choices; it does not establish the security of a complete cipher.

## How to think about it

Search outside the paper’s restricted matrix patterns. Reject candidates quickly when a derivative has the wrong rank. Treat inequivalence as a separate obligation after APN testing.

## What counts as a solution

Give a quadratic homogeneous polynomial of the specified binary-coefficient form over GF(2^11), prove by exhaustive evaluation that it is APN, and supply an independently checkable certificate that it is CCZ-inequivalent to each of the six Table 3 representatives. A sufficient certificate is an ortho-derivative differential/Walsh spectrum signature different from that of every representative, using the invariant theorem for quadratic APN functions cited in the paper. Merely finding a different truth table or a seventh output of a heuristic classifier is insufficient.

Specify an irreducible binary degree-11 modulus; independently verify irreducibility and build exact field arithmetic. Expand F and each reference function on all 2048 inputs. Check all 2047 nonzero differences and all 2048 inputs, requiring difference counts 0 or 2. For each a≠0, form the linear derivative x↦F(x+a)+F(x)+F(a)+F(0); its image has rank 10. Compute its unique nonzero orthogonal normal vector by GF(2) elimination to obtain the ortho-derivative. Recompute its full differential spectrum and component Walsh spectra. Compare invariant histograms with all six references. Include the cited invariant justification; an alternative inequivalence certificate must have a complete exact replay, not a failed equivalence search.

## Our approach

Use a bounded structured search. Verify all field arithmetic, all differences and the invariant spectra independently. No new function is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://link.springer.com/article/10.1007/s00200-025-00711-8>
- <https://link.springer.com/article/10.1007/s00200-025-00711-8/tables/3>
