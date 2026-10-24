# Exact certificates for eight SMT-COMP P4/DFA holdouts

**Open problem.** Can one listed SMT-COMP 2026 P4/DFA instance receive a checked SAT or UNSAT certificate?

**Status.** SMT-COMP 2026 metadata marks eight Xiaoqi Chen P4/DFA QF_BV files unknown. On 2026-10-24 each has 23 single-query runs, all Timeout or unknown; the parallel, model-validation and unsat-core logs contain no runs for these eight paths. Under QF_BV/20221214-p4dfa-XiaoqiChen/ the files are Composition/compose.s4._bit8_na6_nr4_paired.smt2; StringMatching/string2x16.10._bit8_na6_nr3_paired.smt2; StringMatching/string4x16.2._bit8_na6_nr4_pairedtwobranch.smt2; StringMatching/string4x8.2._bit8_na6_nr3_paired.smt2; StringMatching/string4x8.3._bit16_na6_nr4_paired.smt2; StringMatching/string4x8.5._bit8_na6_nr3_paired.smt2; StringMatching/string4x8.8._bit16_na6_nr4_paired.smt2; TCP/tcp_full_split4_bit8_na6_nr4_paired.smt2. The metadata reports 4969 assertions for the TCP file. This confirms no SAT/UNSAT result in the checked 2026 public logs, not the absence of private solutions. Original benchmark bytes and checksums were not retrieved in this preparation. Finite bit-vector SMT differs from the upstream SAT Competition instances.

Status checked: 2026-10-24 (unknown metadata joined to all four non-incremental 2026 result logs; original SMT-LIB files not fetched). [Status source](<https://raw.githubusercontent.com/SMT-COMP/smt-comp.github.io/master/data/benchmarks-2026.json.gz>).

## The problem

Each named file is a quantifier-free bit-vector formula. Decide whether all assertions have a simultaneous model under exact SMT-LIB semantics. The exact eight paths are listed in the proposal.

## Backstory

The fetched 2026 metadata marks all eight unknown. Each has 23 single-query runs with only Timeout or unknown outcomes. The other three checked non-incremental tracks contain no runs for these files. The TCP metadata reports 4969 assertions.

## Why it matters

A checked model or proof converts an unresolved public benchmark into an exact result. A bare solver status is insufficient.

## Real-world uses

The benchmark names refer to P4/DFA composition, string matching and TCP. Establishing the original engineering interpretation requires inspecting the actual formula.

## How to think about it

Download the unmodified original and record its hash before search. Bit-vector arithmetic wraps at fixed widths; signed operations and exceptional cases must use SMT-LIB semantics. For UNSAT, every preprocessing and bit-blasting step needs a checked translation.

## What counts as a solution

Decide any one of the eight exact benchmark instances with an independently checked SAT model or UNSAT certificate. Identify the official SMT-LIB file path and SHA-256 of the unmodified downloaded input. A SAT answer needs a total assignment satisfying every assertion under exact SMT-LIB bit-vector semantics. An UNSAT answer needs a checked bit-blasting translation plus a replayable SAT proof, or another independently checkable theory proof. A bare solver answer, timeout change or solution of a simplified non-equivalent instance does not win.

For SAT, parse the original SMT-LIB input and evaluate all terms under the submitted assignment using width-bounded integers, including signed operations, shifts, overflow and division-by-zero semantics. For UNSAT, independently reconstruct or certify every preprocessing/bit-blasting step, and validate the resulting LRAT or comparably explicit proof. Verify that the CNF proved UNSAT is equisatisfiable with the original assertions. Accept only certificates that a reviewer can check within hours on one laptop; search runtime itself is not evidence.

## Our approach

Inspect repeated automaton structure and try semantics-preserving simplification. Prefer small independently checkable certificates. Only metadata and result logs were fetched here; no original formula or new decision is claimed.

New candidate certificates use the bank’s commit-only disclosure rule. This preparation submits nothing.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://smt-comp.github.io/2026/results/qf_bitvec-single-query/>
- <https://smt-comp.github.io/2026/results/>
- <https://raw.githubusercontent.com/SMT-COMP/smt-comp.github.io/master/data/benchmarks-2026.json.gz>
- <https://raw.githubusercontent.com/SMT-COMP/smt-comp.github.io/master/data/results-sq-2026.json.gz>
- <https://raw.githubusercontent.com/SMT-COMP/smt-comp.github.io/master/data/results-mv-2026.json.gz>
- <https://raw.githubusercontent.com/SMT-COMP/smt-comp.github.io/master/data/results-parallel-2026.json.gz>
- <https://raw.githubusercontent.com/SMT-COMP/smt-comp.github.io/master/data/results-uc-2026.json.gz>
