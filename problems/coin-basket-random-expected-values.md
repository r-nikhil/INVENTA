# Optimal coin placement into randomly chosen baskets

**Open problem.** A basket is chosen uniformly at random, then you choose which remaining coin to put in it. How large can the expected final largest basket be? Compute A391791(n) for n=23,…,25 and A391792(n) for n=19,…,21, where A(n)=k^(n−1) times the optimal expected payoff for k baskets.

**Status.** The listed OEIS sources could not be retrieved. The computation ranges below are targets from the supplied proposal; this check does not establish the current extent of either sequence. [Status source](<https://oeis.org/A391791>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. The earlier page review was dated 2026-10-15. This preparation made no new source request.

## The problem

Coins have values 1,…,n and are each used once. Basket choices are independent and uniform, and the player sees the chosen basket before selecting a coin. With remaining set R and sums s, V(R,s)=(1/k)∑_b max_{c∈R}V(R∖{c},s+c e_b), with V(∅,s)=max(s); e_b is the unit vector for basket b. For example, the supplied n=3 terms give expected values 20/2²=5 for two baskets and 40/3² for three. The published scale is k^(n−1). An integer table stores W(R,s)=k^|R|V(R,s), and the initial W value is divided by k for the sequence term because the first basket choice is equivalent by symmetry.

## Backstory

- 2025-12-20: The two-basket entry was added.
- 2025-12-31: The three-basket entry was added.

## Why it matters

The decision is adaptive: the coin can respond to the revealed basket. This makes the game an exact test of how timing and partial control affect expected rewards.

## Real-world uses

Exact values compare placement heuristics and benchmark stochastic dynamic programming. Optimal first-move sets can also test the entry’s conjectured opening rule.

## How to think about it

For two baskets, the remaining set determines the placed total, so only the absolute difference of basket sums is needed. Three baskets require a fuller sorted profile. Layered computation can reduce memory, but the recursion must still optimize over every adaptive coin choice.

## What counts as a solution

Compute all six specified sequence terms with two independently written programs using only exact integer or rational arithmetic in value calculations. They must agree on every new term and reproduce all earlier available terms for each sequence. Check the original definitions, entries, b-files and edit histories. Three new terms of only one sequence count as partial progress. Exact optimal first-move sets can confirm the proposed coin floor((n+3)/2) on a tested range or refute it at a certified counterexample; a finite confirmation is not a universal proof.

## Our approach

Use layered exact dynamic programming with symmetry-reduced basket states. Independently recompute the sequences with a different state representation and verify the scaling.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://oeis.org/search?q=baskets+coins+expected&fmt=text> — HTTP 403; not retrieved.
- <https://oeis.org/search?q=id:A391537|id:A391538&fmt=text> — HTTP 403; not retrieved.
- <https://oeis.org/search?q=%22optimal+strategy%22+keyword:hard&fmt=text> — HTTP 403; not retrieved.
- Status source: <https://oeis.org/A391791> — HTTP 403; not retrieved.
