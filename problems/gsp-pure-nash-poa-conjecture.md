# Can stable ad-slot bids waste more welfare?

**Open problem.** In a generalized second-price auction, bidders compete for slots with different click rates. Can a pure Nash equilibrium with each bid no greater than its bidder’s value have OPT/SW exceed the exact three-slot supremum, reported near 1.259134? Such an instance would exceed the supplied three-slot threshold and refute the conjectured bound for every number of slots.

**Status.** The cited work gives a lower example near 1.259133 and the upper bound (61+7√217)/128, approximately 1.28216. Lucier and Paes Leme conjectured that the three-slot bound extends to all slot counts. Ding and coauthors’ 2013 preprint claims a four-slot result; its proof has not been independently verified in this check. [Status source](<https://arxiv.org/abs/2609.39532>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

Values v_i are per click; slot click rates satisfy α_1 ≥ … ≥ α_n ≥ 0. Bids determine the ranking, and each winner pays the next lower bid per click. Utility is α_slot(v_i−price); welfare SW is ∑α_slot v_i. OPT pairs the highest values with the highest click rates. For example, the cited two-slot values and rates (1,1/2), with bids (0,1/2), give a welfare ratio of 5/4.

## Backstory

- 2010: Lucier and Paes Leme stated the conjecture.
- 2013: Ding and coauthors posted the cited four-slot and cyclic-ranking note.
- 2015: Caragiannis and coauthors published the cited equilibrium bounds.
- 2026-09-30: Kroll and coauthors restated the old lower bound while studying a weaker aggregate no-overbidding condition.

## Why it matters

High-value participants can bid into low slots when incentives and prices make that stable. The welfare ratio quantifies the loss in value created by the allocation, rather than the seller’s revenue.

## Real-world uses

A certified instance can test auction simulators and identify limits of position-auction efficiency guarantees. It must keep the per-bidder bid cap; changing to an aggregate cap changes the question.

## How to think about it

An inefficient ranking need not be supportable by equilibrium bids. Search must find values, click rates and actual bids that block every profitable move to another slot. Ties and bids at ranking boundaries require exact treatment.

## What counts as a solution

Give rational values, rates and bids with 0 ≤ b_i ≤ v_i and a deterministic tie rule. Verify every bidder’s utility against every attainable slot under any allowed deviation, including boundary ties. Compute OPT and SW exactly and prove OPT/SW > 1.259134. Calibrate on the cited two- and three-slot examples using source-accurate parameters and conventions. A merely weakly feasible allocation is insufficient; a three-slot candidate above the proved bound indicates a verification error. Check later bounds before claiming.

Any exact symbolic certificate above the exact three-slot supremum counts without a minimum gap. The displayed 1.259134 threshold is numerical. Use the source-defined exact calibration instance if rounded parameters do not satisfy the Nash inequalities. Printed numerical outputs use tolerance within one unit of the last printed digit.

## Our approach

Search nontrivial rankings and optimize bids and values subject to equilibrium constraints. Independently test all slot-changing deviations and the exact welfare ratio.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/pdf/1201.6429>
- <https://arxiv.org/pdf/1011.3268>
- <https://arxiv.org/pdf/1305.5404>
- <https://arxiv.org/pdf/2609.39532>
- Status source: <https://arxiv.org/abs/2609.39532>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
