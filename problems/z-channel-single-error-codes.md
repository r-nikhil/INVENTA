# More codewords for one-way bit errors

**Open problem.** How many messages can be encoded when a transmission may change one 1 into a 0? For distinct binary words x and y, define N(x,y) as the number of positions with x_i = 1 and y_i = 0. A single-error-correcting Z-channel code requires max(N(x,y),N(y,x)) ≥ 2 for every pair. Improve the known sizes at lengths 10, 11 or 12, or prove that 112 is optimal at length 10.

**Status.** The listed OEIS entry and challenge page could not be retrieved. The proposed construction baselines 112, 198 and 379 for lengths 10, 11 and 12 come from the supplied proposal; this check does not establish them as current records. [Status source](<https://oeis.org/A010101/internal>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

The error is directional: a 0 cannot become a 1. As an illustrative example, 00 and 11 can coexist because the words obtainable by at most one allowed error are {00} and {11,01,10}, which do not overlap. In contrast, 00 and 01 conflict. Equivalently, choose an independent set in the graph whose vertices are binary words and whose edges join conflicting pairs.

## Backstory

- 1998: Etzion and Östergård supplied the cited ranges.
- 2001: Butenko and coauthors improved the length-12 lower bound to 379.
- December 2015: The input dates Sloane’s challenge-page update to this month.
- 2020-08-24: The input dates the referenced OEIS entry’s last edit to this day.

## Why it matters

A channel’s error model changes the right code. Designing specifically for one-way errors can avoid restrictions needed for arbitrary flips. The same problem also supplies a concrete test of exact independent-set search and proof certificates.

## Real-world uses

An explicit codebook supports encoding and single-error correction for the stated directional channel. The associated graphs can benchmark optimization tools without needing private data or a hardware measurement.

## How to think about it

The challenge is to pack many words while avoiding every confusable pair. Search can exploit coordinate permutations and group words by their number of ones. Construction search and upper-bound proofs are different tasks: a better code raises the guaranteed achievable size, while a checked impossibility argument limits every code.

## What counts as a solution

For n ∈ {10,11,12}, supply a distinct-word code strictly larger than the best published construction at verification time, exceeding the supplied baselines 112, 198 or 379 as applicable. Check every pair directly and independently verify the corresponding independent set in the cited graph. Alternatively, certify that the length-10 maximum is exactly 112 with an accepted proof for a complete encoding. Certified upper bounds below 117, 210 or 410 are partial targets. Do not confuse these records with single-deletion codes or ordinary Hamming-distance codes.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

## Our approach

Search compatible word sets using weight layers and coordinate symmetries. Independently check all word pairs, and pursue certificate-producing exact search for the smallest unresolved case.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://oeis.org/A010101/internal> — HTTP 403; not retrieved.
- <https://oeis.org/A265032/a265032.html> — HTTP 403; not retrieved.
- <https://arxiv.org/abs/2309.14736>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
