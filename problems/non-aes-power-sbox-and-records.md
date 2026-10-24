# Fewer AND gates for five small power S-boxes

**Open problem.** Can a listed non-AES power S-box use fewer AND gates at depth two?

**Status.** Marie Bolzer, Sébastien Duval and Marine Minier, A Tool for Lightweight (AND, XOR) Implementations of Large-Degree S-boxes, TCHES 2026(2), 605–629, ask about optimal (AND depth, AND count) in section 7.4. Tables 4 and 6 give depth-two implementations: in GF(32), x^30 uses 12 ANDs and x^21 and x^25 use 10 each; in GF(128), x^7 uses 30 and x^11 uses 27. The polynomial bases use z^5+z^2+1 and z^7+z+1. The XOR counts are respectively 51,37,37,140,115. Here x^30 is inversion with zero mapped to zero; x^21 and x^25 invert x^3 and x^5 as permutations. These five exact functions are outside the upstream AES and binary-multiplier targets.

Status checked: 2026-10-15 (supplied literature-status date; primary publication re-read 2026-10-24, later literature not independently rechecked). [Status source](<https://tches.iacr.org/index.php/TCHES/article/download/12901/12528>).

## The problem

The five functions are x^30, x^21 and x^25 in GF(32), and x^7 and x^11 in GF(128). Use the published polynomial bases. AND depth counts the AND gates on a path; XOR and NOT add no multiplicative depth.

## Backstory

Bolzer, Duval and Minier’s 2026 paper reports AND counts 12,10,10,30,27 at depth two and explicitly asks about optimality. The paper also supplies XOR counts, but this target constrains only AND count and depth.

## Why it matters

A smaller circuit at the same nonlinear depth improves a precise implementation trade-off. Increasing depth changes the target.

## Real-world uses

These functions serve as small cryptographic substitution components and circuit-synthesis benchmarks. Gate counts alone do not certify resistance to side channels.

## How to think about it

Share quadratic intermediates across outputs and consider affine-equivalent internal bases. Include the complete input and output conversions. Test all 32 or 128 inputs.

## What counts as a solution

Give a complete acyclic circuit for any one of these five exact vectorial functions, with AND depth at most 2 and respectively at most 11, 9, 9, 29 or 26 binary AND gates. Binary XOR and NOT, constants and fan-out are allowed; list and count every gate. NOT and XOR have zero multiplicative depth. No bound is imposed on XOR count, but all affine input/output conversions must appear in the circuit. Outputs must equal the specified field power in the specified basis, for every input. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar.

Independently implement polynomial-basis field arithmetic by carryless multiplication and reduction. Evaluate the candidate on every 5- or 7-bit input and compare all output bits with repeated-squaring exponentiation. Check the DAG, gate types, AND count and maximum number of AND nodes on any input-output path. Recompute algebraic degree by a Boolean Möbius transform as a consistency check. The truth tables and integer gate counts need seconds, not probabilistic testing.

## Our approach

Use the published synthesis ideas and local exact resynthesis, then independently recount gates and verify truth tables. No improved circuit is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://tches.iacr.org/index.php/TCHES/article/download/12901/12528>
- <https://tches.iacr.org/index.php/TCHES/article/view/12901>
- <https://github.com/seduval/implem-sbox>
