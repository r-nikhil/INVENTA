# Can two small constrained allocations unlock four-agent fairness?

**Open problem.** Do both key matroids admit EF1 with ordered no-envy?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2608.31121>).

## The problem

Four agents must divide either eight or twelve goods while obeying group and total bundle limits. Can they always achieve EF1 and avoid envy from each earlier agent to every later agent in a prescribed order?

## Backstory

Benjamin Cookson and Nisarg Shah reduce four-agent laminar-matroid fairness to these two finite questions in their August 2026 paper. Section 5 and Appendix B leave the required allocations open. Lemma 12 only refutes a proposed proof strategy.

## Why it matters

The small cases are bottlenecks in a reduction that would establish a broader four-agent existence result under laminar constraints.

## Real-world uses

Such constraints model category caps and nested capacity limits in resource allocation. Exact small examples can test fair-allocation software.

## How to think about it

The eight-good groups have sizes 3,3,2; every bundle has two goods. The twelve-good case has four groups of three; every bundle has three goods. A bundle takes at most one good per group. EF1 allows removal of the envied bundle’s most valuable good, while ordered no-envy requires no removal.

## What counts as a solution

Give a rational valuation matrix that defeats every feasible allocation in either case, or a machine-checkable universal existence proof for both cases. A universal proof for one case is a partial win. An obstruction concerns the stronger ordered property and need not refute ordinary EF1.

## Our approach and status

Independent enumeration confirmed 864 and 31104 feasible labeled allocations. Search adversarial valuations and independently check every feasible allocation. Those counts describe search spaces; they settle neither question.

## Sources

- <https://arxiv.org/pdf/2608.31121>
