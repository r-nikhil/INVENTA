# Does matching a rival’s stack reduce first-bust risk?

**Open problem.** Three players repeatedly face random fair all-in contests. Let f(x,y,z) be the chance that player 1 is eliminated first. Angel–Holmes Conjecture 9 asks whether f(x,y,z) > f(y,y,z) for every positive real x,y,z with x<y: does raising the short stack exactly to its rival’s level always help?

**Status.** He and Holmes prove a related ordering theorem in their 2024 paper and state Conjecture 9 as future work in Section 5.3. The repository README identifies a yyz module studying the same comparison, but does not establish a resolution of it. [Status source](<https://arxiv.org/abs/2410.15329>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. The earlier page review was dated 2026-10-15. A computer-assisted proof was submitted in V3R1T4S PR #192; the maintainer reproduced its certificates but closed the PR on 2026-10-24, because the repository records only machine-checkable results and a proof needs peer review. The conjecture is not established by this submission. This preparation made no new source request.

## The problem

Each round selects one of the three unordered pairs uniformly and flips a fair coin. The loser pays the smaller of the two stacks to the winner; hitting zero ends the first-elimination contest. Each pair-and-winner transition has probability 1/6. For example, stacks 1 and 2 become either 0 and 3 or 2 and 1. In the conjectured comparison, the third stack remains z and the total changes; this is not a redistribution at fixed total.

## Backstory

- He and Holmes cite Angel and Holmes’s “All In” poker sequences as an unpublished manuscript, without a publication date, and attribute the earlier conjectures and nonmonotonicity result to it.
- 2024-10-20: He and Holmes posted a computer-assisted proof of the companion ordering theorem.
- 2024: Section 5.3 of that paper reported that the Conjecture 9 computation became too slow beyond its attempted depth.

## Why it matters

Tournament elimination risk need not behave like a simple smooth function of chip count. This fair-coin model isolates stack geometry from card skill and asks which comparative intuitions actually survive.

## Real-world uses

Exact ruin probabilities can test all-in tournament approximations and provide examples where general monotonicity intuition fails. They do not substitute for a card-dependent tournament model.

## How to think about it

Transitions change when stack sizes cross, so the function has difficult boundaries. Still, each round ends the contest with probability at least 1/2. If h_n is the exact probability of player 1 busting first within n rounds, then f lies in [h_n,h_n+2^−n], giving rigorous finite-depth bounds.

## What counts as a solution

For a counterexample, give positive rationals x,y,z with x<y and certify f(x,y,z) ≤ f(y,y,z). The proposal’s sufficient certificate is h_n(x,y,z)+2^−n ≤ h_n(y,y,z), independently checked in exact or outward-rounded arithmetic. Alternatively prove the strict inequality for all permitted real stacks using a gap-free formal proof or an independently checked region partition and exact bounds. A failure to certify a gap at finite depth is not a counterexample. A checked proof on any one of z≥y, z≤x, or x<z<y is partial progress. The proof submitted in PR #192 remains PROMISING pending expert checks of two analytic lemmas.

## Our approach

Search rational stack ratios near transition boundaries using exact finite-depth enclosures. If pursuing a proof, partition the normalized parameter space and independently verify each region’s bounds.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2410.15329>
- <https://arxiv.org/pdf/2410.15329>
- <https://github.com/7angel4/betting-game-proof>
- <https://arxiv.org/abs/2011.07610>
- Repository status update supplied for this preparation: <https://github.com/elder-plinius/V3R1T4S/pull/192>.
