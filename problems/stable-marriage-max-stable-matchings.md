# How many stable matchings can a marriage market have?

**Open problem.** Take *n* men and *n* women who each rank everyone on the other side. A matching is *stable* if no man
and woman would both rather be with each other than with their partners. What is the largest number *f(n)* of stable
matchings an instance of size *n* can have? Exact values are known only for *n* ≤ 5; for larger *n* the best we have
are explicit instances (lower bounds) and an upper bound of about 3.55ⁿ.

**Status.** Best known lower bounds: OEIS [A357271](https://oeis.org/A357271) and its instance file (Ong et al.); exact
values: OEIS [A357269](https://oeis.org/A357269). Proposed to the V3R1T4S bank:
[draft PR #153](https://github.com/elder-plinius/V3R1T4S/pull/153) (2026-10-15).

## The problem

Every stable-marriage instance has at least one stable matching (Gale and Shapley, 1962), and the stable matchings
form a *distributive lattice*: the men-optimal matching at one end, the women-optimal at the other, and every stable
matching in between is reached by a sequence of *rotations* (cyclic exchanges of partners). Counting the stable
matchings of a given instance is #P-complete (Irving and Leather, 1986), but it is fast in practice for *n* up to a few
dozen, because the matchings correspond to the closed subsets of a small partial order (the rotation poset).

The question is the extreme case: which preference lists make that lattice as large as possible?

## Backstory

- **1976.** Donald Knuth, *Mariages stables*, asks how many stable matchings an instance can have.
- **1986.** Irving and Leather build instances by "doubling" that reach 1, 2, 10, 268 and 195,472 stable matchings at
  sizes 1, 2, 4, 8 and 16 (OEIS A005154).
- **1989.** Gusfield and Irving list the maximum as Open Problem 1 in *The Stable Marriage Problem*.
- **2002.** Edward Thurber combines smaller instances to give lower bounds for every *n* and proves *f(n)* strictly
  increasing; his values still make up the OEIS A357271 data line.
- **2018–2021.** Karlin, Oveis Gharan and Weber prove an upper bound of the form *cⁿ*; Palmer and Pálvölgyi tighten it
  to 3.55ⁿ.
- **2022.** Dan Eilers creates OEIS A357269 (exact values, *f*(5) = 16 by a MiniZinc model) and A357271 (lower bounds).
- **2024–2025.** Ong, Ang, Ho, Eilers, Marks and Buzi improve the odd sizes 7 to 15 by computer search (for example
  27,059 at *n* = 15).

## Why it matters

Stable matching is the engine of real two-sided markets — medical residency (the US National Resident Matching
Program), school choice in New York and Boston, and the work honoured by the 2012 Nobel Prize in Economics (Roth and
Shapley). The number of stable matchings measures how much freedom a market designer has: which side the outcome
favours, how fair a "median" compromise can be, and how much participants might gain by misreporting. *f(n)* is the
extreme of that freedom, and a basic constant of two-sided markets that is still unknown.

## Real-world uses

- Market design: understanding how many legitimate outcomes a clearinghouse chooses between.
- Algorithms: worst-case inputs for enumeration and counting algorithms, and benchmarks for #P-hard counting.
- Combinatorics: large distributive lattices realised by preference data.

## How to think about it

- **Count fast, search wide.** An exact counter (closed subsets of the rotation poset, cross-checked by a lattice walk)
  turns this into an optimisation problem; local search over preference lists — small swaps, sideways moves, random
  kicks — has produced every recent record.
- **Compose and double.** Old constructions combine small instances into large ones. They are only as good as the blocks
  you feed them, so new record blocks can lift other sizes too.
- **Structure.** The record instances have highly symmetric rotation posets; explaining why could lead to explicit
  families and better growth rates than about 2.28ⁿ.
- **Exact cases.** Proving *f*(6) needs an exhaustive search with sound symmetry breaking and a checkable proof object.

## What counts as a solution

Explicit preference lists for some *n* ≥ 6 whose stable matchings, counted exactly by two independent methods,
strictly outnumber the best known value for that *n*. Partial win: a machine-checked proof of the exact value *f*(6).
Anyone can verify a claimed instance in seconds.

## Our approach and status

We attack this with V3R1T4S research lanes: an exact counter, iterated local search from the published records, and
the classic doubling applied to new record blocks. Results so far that passed the full gauntlet and were submitted:
[001](../results/001-stable-marriage-n15.md) and [004](../results/004-stable-marriage-n15-30362.md) (*n* = 15),
[002](../results/002-stable-marriage-n18.md) (*n* = 18), [003](../results/003-stable-marriage-n13.md) (*n* = 13),
[005](../results/005-stable-marriage-n14.md) (*n* = 14) and [006](../results/006-stable-marriage-n22.md) (*n* = 22).
Other sizes are posted only after independent verification.

## Sources

- OEIS [A357271](https://oeis.org/A357271) (and its instance file [a357271_1.txt](https://oeis.org/A357271/a357271_1.txt)),
  [A357269](https://oeis.org/A357269)
- C. Palmer, D. Pálvölgyi, [arXiv:2011.00915](https://arxiv.org/abs/2011.00915) (the 3.55ⁿ upper bound);
  A. Karlin, S. Oveis Gharan, R. Weber, "A simply exponential upper bound on the maximum number of stable matchings",
  STOC 2018
- R. W. Irving, P. Leather, SIAM J. Computing 15 (1986); E. G. Thurber, Discrete Mathematics 248 (2002);
  D. Gusfield, R. W. Irving, *The Stable Marriage Problem* (MIT Press, 1989); D. E. Knuth, *Mariages stables* (1976)
