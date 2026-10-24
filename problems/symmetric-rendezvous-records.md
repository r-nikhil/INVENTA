# Meet sooner without a shared direction

**Open problem.** Two identical searchers must meet without agreeing who waits or which way is left. On a line they start distance 2 apart, move at speed at most 1, and use the same synchronized randomized rule with independent randomness. Can their expected meeting time be certified at most 4.2573, or can the universal lower bound be raised to 4.1521?

**Status.** The cited September 2026 paper reports the line bounds 4.1520 ≤ R ≤ 4.2574, attributed to Han, Du, Vera and Zuluaga. For the separate four-location problem, Cembrano, Fischer and Klimm’s cited FSD strategy supplies the comparison target. [Status source](<https://arxiv.org/pdf/2609.13632>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

R is the infimum expected meeting time over admissible symmetric strategies. Each searcher interprets a move in their own orientation. For illustration, moving inward from distance 2 at unit speed meets after one time unit, but moving outward does not; neither agent can assume a shared orientation or assigned role. The discrete-location variant instead uses independently randomized labels and allows meeting at time zero.

## Backstory

- 1990: Anderson and Weber studied symmetric rendezvous on discrete locations.
- 1995: Alpern’s line strategy gave expected time 5.
- 2008: Han and coauthors established the supplied line bounds using finite-path strategies and optimization.
- 2026: Cembrano and coauthors improved the discrete-location strategy for n ≥ 4.

## Why it matters

This is a coordination problem under missing common reference information. It captures why identical autonomous participants may need randomness to meet even when their distance or location set is known.

## Real-world uses

Explicit strategies provide benchmarks for decentralized meeting rules and exact evaluation of randomized protocols. The model’s speed, synchronization and independence assumptions define the scope of the guarantee.

## How to think about it

Path choices interact: a route useful against one opponent path may miss another. Finite-state rules make evaluation possible, but may miss better strategies. A lower bound must cover all permitted strategies, not merely the class searched. Meetings during a step must count.

## What counts as a solution

For the line, give a finite explicit symmetric strategy with independently certified expectation ≤ 4.2573, or a rigorous universal lower bound ≥ 4.1521. Alternatively, for four locations with time-zero meeting allowed, give a strategy with expectation strictly below the exact minimum over θ ∈ [0,1) of FSD(θ). Any exactly certified strict improvement counts. Use exact rational or rigorous interval evaluation and beat later published bounds too. A smaller improvement over the exact 2008 strategy is a separate partial target; comparing rounded decimals alone is insufficient.

## Our approach

Optimize distributions over paths or small finite-state rules, then evaluate the joint meeting process independently. Use exact renewal equations or rigorously enclosed expectations for final comparisons.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/pdf/2609.13632>
- <https://arxiv.org/pdf/1805.03351>
- <https://optimization-online.org/2006/05/1400/>
- <https://arxiv.org/abs/2604.02058>
- <https://arxiv.org/pdf/2604.02058v2>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
