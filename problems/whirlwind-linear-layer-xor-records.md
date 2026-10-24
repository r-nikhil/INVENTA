# Smaller XOR circuits for the Whirlwind M0 and M1 maps

**Open problem.** Can the exact Whirlwind M0 or M1 map beat its published binary-XOR count?

**Status.** Buji Xu and Xiaoming Sun, Utilizing Circulant Structure to Optimize the Implementations of Linear Layers, IACR ToSC 2026(2), Table 4, gives binary-XOR implementations of the 32-by-32 Whirlwind M0 and M1 maps with 159 and 169 gates. The prior comparable counts shown are 173 and 180. The separate CNOT quantum-depth tables optimize a different objective. Appendix C supplies the 159-XOR M0 circuit; the authors’ circulant_synth repository describes its synthesis tool. The reference repository supplies both 32-by-32 binary matrices. NIST’s older catalogue was retrieved, but its entries do not replace the newer paper’s counts.

Status checked: 2026-10-15 (supplied literature-status date; primary publication re-read 2026-10-24, later literature not independently rechecked). [Status source](<https://tosc.iacr.org/index.php/ToSC/article/download/13012/12590>).

## The problem

M0 and M1 are fixed 32-bit linear maps. A candidate is a straight-line program of two-input XOR gates with free fan-out and wire naming. The objectives are fewer than 159 or 169 XORs, without a depth constraint.

## Backstory

Xu and Sun’s 2026 Table 4 improves the earlier comparable 173 and 180 counts to 159 and 169. Appendix C gives the M0 implementation. Separate tables for quantum CNOT depth do not set this bar.

## Why it matters

Linear-map synthesis is a compact exact optimization problem. Small gate reductions are easy to verify once the target matrix and bit order are fixed.

## Real-world uses

Diffusion maps are components of cryptographic hardware and bitsliced implementations. Lower gate count can reduce area, while timing depends on the full implementation.

## How to think about it

Exploit circulant blocks and shared subexpressions, or resynthesize small pieces exactly. Input and output basis changes count. Compare against composed published circuits under the same two-input gate model.

## What counts as a solution

Supply a straight-line circuit using only two-input XOR, input wires, the zero constant and free fan-out/wire renaming, computing the exact published 32-bit Whirlwind M0 map with at most 158 XORs, or M1 with at most 168 XORs. Include the 32 target binary rows copied from the cited matrix definition, their bit-order convention, the entire circuit, and output-wire mapping. Count any nontrivial basis conversion. There is no depth constraint. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar.

Represent input wire i by the 32-bit unit vector 1<<i. Propagate XOR coefficient vectors through every assignment and compare the 32 output vectors with an independently transcribed expansion of the published matrix. Validate the gate DAG and count all XOR assignments. Cross-check the target expansion against the published reference circuit or dataset, rather than accepting a claimant-supplied target matrix. Reversible in-place assignments can be expanded into ordinary SSA wires before counting.

## Our approach

Use randomized synthesis with an independent coefficient-vector checker. Propagate a 32-bit unit vector through every XOR and compare all output rows with the published matrix. No smaller circuit is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://tosc.iacr.org/index.php/ToSC/article/download/13012/12590>
- <https://tosc.iacr.org/index.php/ToSC/article/view/13012>
- <https://github.com/DerryAlex/circulant_synth>
- <https://csrc.nist.gov/Projects/circuit-complexity/list-of-circuits>
- <https://raw.githubusercontent.com/rub-hgi/shorter_linear_slps_for_mds_matrices/master/matrices_bp_format/Whirlwind_M0.txt>
- <https://raw.githubusercontent.com/rub-hgi/shorter_linear_slps_for_mds_matrices/master/matrices_bp_format/Whirlwind_M1.txt>
