# Smaller verified circuits for AES components

**Open problem.** Can an AES substitution or column-mixing circuit meet a stronger size or depth target in NIST’s exact gate model? The task is to compute SBox, InvSBox, MixColumns or InvMixColumns with a verified circuit that meets a target recorded in the supplied proposal and improves the current comparable record.

**Status.** The fetched repository table lists SBox minimum AND count 28 and minimum total gates 110, InvSBox 28 and 112, and MixColumns 88 XOR gates at depth 5. These are table entries, not a proof of optimality. The NIST web pages were unavailable, so the maintainer targets below are those recorded in the supplied proposal. [Status source](<https://raw.githubusercontent.com/usnistgov/Circuits/master/data/slp/aes/README.md>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

An S-box maps one byte to another; MixColumns is a linear map on four bytes over GF(2). The allowed two-input gates are AND, XOR and XNOR, with no constants or other gates. Column-mixing targets use XOR only. Total gate count includes every operation; depth is the longest input-to-output chain. For example, two independent XORs followed by one XOR use three gates but depth two.

## Backstory

- 2013: The input credits a Boyar–Peralta circuit improved by Calik with the earlier 113-gate S-box mark.
- 2026-08-07: The repository added 29-AND S-boxes.
- 2026-09-24: Nasr contributed 28-AND and low-AND-depth S-boxes.
- 2026-10-04 through 2026-10-08: The supplied record lists successive InvMixColumns improvements.

## Why it matters

Circuit size and depth affect implementation tradeoffs in cryptographic computing. A smaller circuit is useful only if it computes the exact standard function under the same counting model.

## Real-world uses

Verified gate lists can be components of AES implementations and benchmarks for circuit synthesis. Size alone does not certify side-channel behavior or actual execution speed.

## How to think about it

Search can simplify linear layers, share nonlinear products or change internal bases. Input and output basis conversions still count. Optimizing one metric can worsen another, so both the chosen objective and any depth constraint must remain explicit.

## What counts as a solution

Meet at least one proposal-recorded target, after confirming that it remains applicable: SBox or InvSBox with AND count ≤27, total gates ≤105, or total gates ≤120 and depth ≤12; MixColumns with XOR count ≤86, or ≤93 at depth 3; InvMixColumns with XOR count ≤100 and depth ≤6. Also strictly improve the corresponding metric against every comparable current file and later publication. For the combined targets, compare gate counts only among circuits meeting the stated depth budget: 12 for the S-box target, 3 for the constrained MixColumns target, and 6 for InvMixColumns. For AND-count or unconstrained size targets, compare that metric without limits on other resources. Independently test all 256 S-box inputs or the 32 basis vectors of the XOR-only column map, recompute all metrics, and enforce NIST bit order: S-box U0/S0 most significant, mixing bit r of byte b at index 8b+r. Reject constants, illegal gates and invalid wiring.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

## Our approach

Search shared intermediates and optimize linear layers under explicit depth limits. Independently verify the complete standard function and recount every candidate and reference circuit.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://csrc.nist.gov/Projects/circuit-complexity/list-of-circuits> — HTTP 403; not retrieved.
- <https://csrc.nist.gov/projects/circuit-complexity> — HTTP 403; not retrieved.
- <https://github.com/usnistgov/Circuits>
- <https://raw.githubusercontent.com/usnistgov/Circuits/master/data/slp/aes/README.md>
- <https://raw.githubusercontent.com/usnistgov/Circuits/master/data/slp/aes/aes-sbox/README.md>
- <https://raw.githubusercontent.com/usnistgov/Circuits/master/data/slp/aes/aes-mixcols/README.md>
- <https://raw.githubusercontent.com/usnistgov/Circuits/master/data/slp/aes/aes-invmixcols/README.md>
- <https://api.github.com/repos/usnistgov/Circuits/commits?per_page=30>
- <https://raw.githubusercontent.com/usnistgov/Circuits/master/data/slp/aes/aes-sbox/aes-sbox-a32-ad5-g110-gd22-xx78-3.circ.txt>
- <https://raw.githubusercontent.com/usnistgov/Circuits/master/data/slp/aes/aes-mixcols/aes-mixcols-xor88-depth5.circ.txt>
- <https://www.cs.yale.edu/homes/peralta/CircuitStuff/CMT.html>
- <https://tches.iacr.org/index.php/TCHES/article/view/8346>
- <https://tches.iacr.org/index.php/TCHES/article/download/8346/7695>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
