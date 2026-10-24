# The fewest tickets guaranteeing a two-number match

**Open problem.** How many six-number tickets guarantee that at least one ticket matches two numbers in every possible six-number draw? Determine the exact lottery number L(n,6,6,2) for at least one n from 71 through 90, by giving both a working ticket list and a proof that one fewer ticket cannot work.

**Status.** Cushing and Stewart’s cited revision proves the values through n=70, including L(70,6,6,2)=35. Its program output labels L(71,6,6,2)=38 a conjecture. The fetched sources do not establish an exact value there or a complete current repository comparison. [Status source](<https://arxiv.org/abs/2307.12430>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

Each ticket and draw is a six-element subset of {1,…,n}. A design succeeds when every draw intersects some ticket in at least two numbers. For example, a draw containing any pair from a particular ticket is covered by that ticket. Equivalently, connect two numbers whenever some ticket contains both: the resulting graph must have no independent set of six vertices. This lottery condition differs from requiring every pair to occur on a ticket. For an illustrative ticket {1,2,3,4,5,6}, the draw {1,2,7,8,9,10} is covered through the matching pair {1,2}.

## Backstory

- 1996: Füredi, Székely and Zubor supplied the cited general lower bound.
- 1998: Bate and van Rees reported values through n=54; Cushing and Stewart discuss shortcomings in the earlier justification.
- 2024-06-17: Cushing and Stewart’s cited revision established values through n=70 and displayed the unresolved n=71 configurations.

## Why it matters

This is a precise version of lottery wheeling: covering all draws with a smaller set of tickets. A guaranteed two-number match is a combinatorial guarantee; profitability still depends on ticket costs and payouts.

## Real-world uses

An explicit ticket list can be checked independently before use. A matching lower bound establishes whether any system with fewer tickets could possibly provide the same guarantee.

## How to think about it

Building a good design is easier than proving no smaller one exists. The cited approach combines covering designs for upper bounds with structural restrictions around independent sets for lower bounds. The unresolved exceptional configurations are natural places for a certificate-producing search.

## What counts as a solution

Choose 71≤n≤90. Give L valid tickets and exhaustively check every six-number draw, with an independent graph-based check where practical. Prove infeasibility with L−1 tickets using a checked LRAT/DRAT, VeriPB or exact rational integer-program certificate. Explain or cite every reduction and verify that its encoding covers all designs. Confirm L is no larger than any repository bound for the correctly ordered cell (v,k,t,m)=(n,6,2,6), and that no later paper already settled it. A better upper bound alone does not meet this exact-value target; stronger certified lower bounds are partial results.

Include the best valid composition of published objects for the same parameters and metric in the bar, even if it is absent from a printed table. State whether the candidate is a composition. Identify its components and composition rule.

## Our approach

Rebuild the structural reduction around the unresolved configurations and seek independently checkable infeasibility certificates. Pair any lower bound with a fully verified ticket design.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://arxiv.org/abs/2307.12430>
- <https://arxiv.org/pdf/2307.12430>
- <https://coveringrepository.com/> — HTTP 403; not retrieved.
- <https://lottodesigns.altervista.org/>
- <https://lottodesigns.altervista.org/HowToUseThisSite.html>
- <https://lottodesigns.altervista.org/Improvements.html>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
