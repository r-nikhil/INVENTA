# Shorter binary minimal codes for dimensions ten to thirteen

**Open problem.** Can the published binary minimal-code lengths for dimensions 10–13 be shortened?

**Status.** Vladimir Chubenko and Sascha Kurz, Divisible Minimal Codes, Serdica Journal of Computing 18(2), 97–124 (issue year 2024; published 25 June 2025), Table 2, give m(10,2)=28–29, m(11,2)=31–35, m(12,2)=34–38 and m(13,2)=39–43. Here m(k,2) is the minimum length of a k-dimensional binary linear minimal code. Minimality means no distinct nonzero codewords have one support contained in the other. The paper relates these codes to secret sharing and uses generalized circulant constructions. Dimensions 7–9 are exact and excluded. This optimizes minimal-code length; the upstream codetables target optimizes Hamming minimum distance.

Status checked: 2026-10-15 (supplied literature-status date; primary publication re-read 2026-10-24, later literature not independently rechecked). [Status source](<https://serdica-comp.math.bas.bg/index.php/serdicajcomputing/article/download/sjc.2024.18.97-124/pdf>).

## The problem

A binary linear code is minimal when no distinct nonzero codewords have one support contained in the other. The objective is the smallest number of columns in a full-rank generator matrix with this property.

## Backstory

Chubenko and Kurz’s paper settles dimensions seven through nine and reports four unresolved intervals at dimensions ten through thirteen. The journal issue says 2024, but the publisher gives 25 June 2025 as the publication date.

## Why it matters

The target asks for a smaller exact combinatorial object. It is a different optimization from maximizing Hamming minimum distance.

## Real-world uses

Minimal codes help describe access structures in secret-sharing schemes. Their support relations determine which shares can participate in recovery.

## How to think about it

For each nonzero message, collect generator columns where its codeword is zero. They must span a hyperplane of rank k-1. Every failing message provides a concrete search constraint.

## What counts as a solution

Give a full-rank binary generator matrix for a minimal [n,k] code with k=10 and n≤28, k=11 and n≤34, k=12 and n≤37, or k=13 and n≤42. The resulting code must satisfy minimality for all nonzero codewords. No divisibility, quasi-cyclic structure, projectivity or minimum-distance assumption beyond what follows from minimality is imposed. A valid dimension-10 construction would settle m(10,2)=28 using the published lower bound; the other cases improve a published upper bound. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar.

Check that the supplied k-by-n matrix is binary and has rank k over GF(2). For every nonzero message a in GF(2)^k, compute c=aG and collect the columns of G at positions where c is zero. Their rank must be k−1. This is an exact minimality test: a codeword bG is supported within supp(c) precisely when b annihilates those columns; a one-dimensional kernel must be {0,a}. Independently cross-check by enumerating all nonzero codewords and rejecting any pair with a proper support inclusion. The rank version avoids a quadratic pair scan and uses at most 8191 small elimination problems. Check n against the corresponding record after validation.

## Our approach

Start from generalized circulant constructions, then puncture or replace columns. Check the complete unrestricted code and compare published constructions, including valid compositions. No shorter code is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://serdica-comp.math.bas.bg/index.php/serdicajcomputing/article/download/sjc.2024.18.97-124/pdf>
- <https://doi.org/10.55630/sjc.2024.18.97-124>
