# Multiply eight-term binary polynomials with 25 products

**Open problem.** Can the product of two eight-term polynomials over GF(2) be computed using at most 25 bilinear products? The goal is an explicit decomposition of the full polynomial product, retaining all fifteen output coefficients.

**Status.** Covanov’s cited abstract describes exhaustive bilinear-map search and its pruning improvements. The NIST pages could not be retrieved, so this check does not establish a current benchmark or open-problem listing. The 25-product construction remains the proposal’s research target. [Status source](<https://csrc.nist.gov/projects/circuit-complexity>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

GF(2) addition is XOR. A bilinear product multiplies a linear combination of the first input’s coefficients by a linear combination of the second’s. Output coefficients are XORs of those products. For a small illustration, (a₀+a₁)(b₀+b₁), a₀b₀ and a₁b₁ determine the cross coefficient a₀b₁+a₁b₀ by XOR. Here the cost counts such products, not every XOR gate.

## Backstory

- 2012: Barbulescu, Detrey, Estibals and Zimmermann developed the cited bilinear-rank framework.
- 2018: Covanov’s work supplied further pruning methods.

## Why it matters

A better block formula can feed recursive binary arithmetic. It is a structural arithmetic improvement, separate from polishing a particular implementation’s wiring.

## Real-world uses

The formula can be applied when coefficients are themselves binary polynomials, supplying a reusable multiplication component for larger arithmetic circuits.

## How to think about it

The search chooses both input combinations and output recombinations. Restricted families can make search feasible, but failure within one family does not prove rank 25 impossible. All coefficients must be in GF(2); changing the field or computing only a reduced product changes the target.

## What counts as a solution

Give binary matrices U,V of shape 25×8 and W of shape 15×25, allowing unused product slots for a smaller construction. Independently verify ∑_t U_ti V_tj W_kt = 1 when i+j=k and 0 otherwise, over GF(2), for all 0≤i,j≤7 and 0≤k≤14. These 960 identities certify the full bilinear map; exhaustive evaluation of all 2^16 input pairs is an additional check. Establish the applicable prior bounds and compare later literature before claiming the first such construction. Field-multiplier gate improvements are separate partial targets.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

A checked proof that no bilinear algorithm with at most 25 products exists is also a full answer. Use a complete encoding of the tensor decomposition and a proof accepted by a formally verified checker.

## Our approach

Search binary tensor decompositions near known multiplication formulas. Independently check the complete coefficient identity and the induced polynomial circuit. The other full route is a verified impossibility proof for rank at most 25, using a complete encoding and an accepted proof object.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://csrc.nist.gov/projects/circuit-complexity> — HTTP 403; not retrieved.
- <https://csrc.nist.gov/Projects/circuit-complexity/list-of-circuits> — HTTP 403; not retrieved.
- <https://www.cs.yale.edu/homes/peralta/CircuitStuff/CMT.html>
- <https://arxiv.org/abs/1705.07728>
- <https://binary.cr.yp.to/m.html>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
