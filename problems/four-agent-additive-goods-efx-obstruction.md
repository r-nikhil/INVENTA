# Can four people always divide goods with EFX fairness?

**Open problem.** Is there a finite four-agent additive EFX obstruction?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2608.08590>).

## The problem

Four agents give positive additive values to indivisible goods. Is there an instance for which every complete allocation violates envy-freeness up to any good, or EFX?

## Backstory

Eyad Alkassar, Mahmoud Fouz and Kurt Mehlhorn’s 2026 preprint establishes complete EFX0 allocations for four additive agents and at most nine goods. Its introduction leaves the unrestricted additive question open. Published submodular counterexamples use a different valuation class.

## Why it matters

EFX asks for envy to disappear after any single good is removed from the envied bundle. Its strength makes it a useful test of whether a fairness rule can always be met.

## Real-world uses

Small exact instances can benchmark fair-allocation algorithms and explain the limits of dividing rooms, equipment or other indivisible resources.

## How to think about it

For each ordered pair i,j, compare agent i’s own bundle value with the value of j’s bundle after removing its least valuable good according to i. Positive values make EFX and EFX0 coincide. All goods must be assigned; extra efficiency or bundle-size conditions would change the question.

## What counts as a solution

Give a positive rational 4-by-m valuation matrix with m>=10 and an exact certificate that every allocation fails. A short independent checker must verify exhaustive coverage or a justified compressed enumeration within a few hours.

## Our approach and status

Search structured integer valuations and use a satisfying allocation to reject each candidate. Certify any surviving obstruction with a separate exhaustive checker. No obstruction is asserted in this proposal.

## Sources

- <https://arxiv.org/pdf/2608.08590>
- <https://arxiv.org/pdf/2606.08872>
