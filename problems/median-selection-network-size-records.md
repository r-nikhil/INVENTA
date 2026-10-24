# Smaller exact median selection networks

**Open problem.** Can an exact median selection network for 10–25 inputs use fewer comparators?

**Status.** Bert Dobbelaere’s maintained List of median selection networks gives explicit size/depth trade-offs. On 2026-10-24, the least listed comparator counts for n=10 through 25 are respectively 22,25,29,32,38,41,46,49,55,58,63,66,74,77,82,85. These are construction records, not proofs of optimality. The page includes updates through 2026-10-16 and credits Mason Hemmer and Touko Ursin. For odd n one designated output is the middle order statistic. For even n two designated outputs are the two middle order statistics, possibly unordered. The page also describes reductions from networks with nearby input sizes. Median selection differs from full sorting and adaptive comparison selection.

Status checked: 2026-10-24 (maintained table and construction rules confirmed; broader later literature not independently rechecked). [Status source](<https://bertdobbelaere.github.io/median_networks.html>).

## The problem

A comparator replaces two values by their minimum and maximum. The same comparator sequence must work for every input. Odd input counts need one middle value; even counts need the unordered middle pair.

## Backstory

Dobbelaere’s maintained table publishes gate lists and size/depth trade-offs. Its latest fetched change log includes 16 October 2026. The least listed counts for the target sizes remain 22,25,29,32,38,41,46,49,55,58,63,66,74,77,82,85.

## Why it matters

Median selection can use fewer comparators than full sorting. This proposal counts comparators; the page’s separate min/max subcomponent cost is another metric.

## Real-world uses

Exact networks can implement median filters and fixed-latency order-statistic hardware. Real execution speed also depends on the implementation.

## How to think about it

Nearby-size trimming and central-output constructions already belong to the bar. Search for a smaller network, then verify every binary input; the threshold principle extends this check to totally ordered inputs.

## What counts as a solution

For any listed n, give an input-independent sequence of compare-exchange pairs, output positions, and an exact correctness certificate, using strictly fewer comparators than the listed minimum for that n. A comparator replaces its ordered pair of wires by (min,max). For even n return the two middle input values as an unordered pair; averaging is outside the network. Count every comparator including any added at the outputs. Depth is reported but unconstrained. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar.

Check pair indices and count comparators, then evaluate every binary input in {0,1}^n using packed bitsets or batches. For odd n the selected bit must be 1 iff the input contains at least (n+1)/2 ones. For even n compare the sorted selected pair with binary order statistics n/2 and n/2+1. The threshold principle for comparator circuits extends this exhaustive binary check to all totally ordered inputs, including ties. A SAT UNSAT certificate for a violating input is an alternative, provided the encoding is independently reconstructed and the proof checked.

## Our approach

Delete and repair comparators or resynthesize a small suffix with SAT. Independently check the whole network. No improved network is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://bertdobbelaere.github.io/median_networks.html>
- <https://github.com/bertdobbelaere/SorterHunter>
