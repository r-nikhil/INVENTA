# Shorter chains for elliptic-curve inversion

**Open problem.** In a prime field, x^(N−2) mod N gives the inverse, while x^(N−3) gives its square. Can one of the eight field or scalar exponents in the cited chain tables be reached with a shorter addition chain than every known chain for that exact exponent?

**Status.** Smith’s page and the addchain results support these reference lengths: field targets, Curve25519 265, P-256 266, P-384 396 and secp256k1 269; scalar targets, Curve25519 283, P-256 292, P-384 433 and secp256k1 290. The P-256, P-384 and secp256k1 field lengths are for N−3, which computes the square of the inverse. The other listed targets use N−2. Comparisons must use the same exact exponent. [Status source](<https://briansmith.org/ecc-inversion-addition-chains-01>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

An addition chain starts at a₀=1 and ends at E=N−d. In the cited tables d=3 for the P-256, P-384 and secp256k1 field targets; d=2 for the Curve25519 field target and all four scalar targets. Each later a_i equals a_j+a_k for earlier indices j,k. Exponents translate into multiplications: x^(a_j+a_k)=x^a_j x^a_k; equal indices give a squaring. As an illustrative chain, 1,2,3,6 reaches exponent 6 in three operations. Both squarings and other multiplications count, while the starting 1 does not.

## Backstory

- 2005–2006: Bernstein supplied the cited Curve25519 field chain.
- 2014–2017: The input records several later field and scalar improvements.
- 2017-09-03: Smith’s cited page was updated and invited shorter chains.
- 2024-06-30: The input dates the referenced addchain results snapshot’s last commit to this day.

## Why it matters

A fixed exponentiation schedule is useful in cryptographic arithmetic. Reducing its operation count can improve that component, although a shorter chain alone does not prove faster hardware performance or a complete constant-time implementation.

## Real-world uses

An explicit chain can be translated into fixed modular-inversion code and used to benchmark exponentiation generators for the listed curves.

## How to think about it

Long runs in a field exponent and irregular scalar-exponent bits favor different decompositions. Reusing intermediate exponents is the main opportunity. The search must count the cost of building the shared dictionary, not just the final combination.

## What counts as a solution

Provide index pairs defining a chain to exactly N−d for the chosen table entry, using its field prime or group order N and its stated d. For the three inverse-square field entries, a chain to N−2 is a different target and must be compared separately. An independent integer checker must validate every sum, final exponent and total length, and compare against the minimum of Smith’s page, addchain and later published or library chains. Re-derive the modulus from the cited curve specifications before claiming. Congruent but different exponents and variable-time inversion methods do not meet this target. Modular tests on nonzero inputs are an additional check, not a replacement for verifying the chain.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

## Our approach

Search exponent decompositions and shared intermediate dictionaries. Independently validate each integer step and compare total operation counts for the exact target exponent.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://briansmith.org/ecc-inversion-addition-chains-01>
- <https://github.com/mmcloughlin/addchain>
- <https://raw.githubusercontent.com/mmcloughlin/addchain/master/doc/results.md>
- <https://arxiv.org/abs/2207.13276>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
