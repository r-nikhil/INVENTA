# When does a two-item auction become deterministic?

**Open problem.** Is the sufficient determinism threshold increasing?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2608.22371>).

## The problem

One buyer values two items independently. D. Thirumulanathan gives a sufficient threshold c2*(c1) above which separate posted prices maximize revenue. Does this threshold increase when the minimum value c1 of the first item increases?

## Backstory

The 2026 paper studies positive, nondecreasing, continuously differentiable densities. Its page-14 footnote explicitly leaves this monotonicity question open. The threshold is a sufficient condition; deterministic optimality can already hold below it.

## Why it matters

A simple price can sometimes achieve the revenue of a much more complicated auction. The question asks whether the paper’s certificate for this simplification behaves predictably as buyers’ minimum values change.

## Real-world uses

The model helps compare auction formats and check mechanism-design software. Its assumptions describe a mathematical benchmark for a single buyer.

## How to think about it

Fix the shapes of both densities and translate their supports. The threshold is the maximum of three quantities, built from the optimal single-item price, a derivative maximum, and a truncated-mean equation. For uniform densities it is 2*b2*b1^2/(b1-c1)^2, which increases on 0<=c1<b1. General density shapes remain the issue.

## What counts as a solution

Give admissible densities and c<c' with a certified strict decrease in c2*, or a machine-checkable proof for the full density class. Exact algebraic or rational certificates can establish any strict decrease. A positive result must specify whether increasing means nondecreasing or strictly increasing and address equality.

## Our approach and status

Search normalized positive polynomial densities, then isolate roots and certify derivative maxima exactly. No counterexample or proof is claimed here.

## Sources

- <https://arxiv.org/pdf/2608.22371>
- <https://doi.org/10.1016/j.jmateco.2026.103293>
