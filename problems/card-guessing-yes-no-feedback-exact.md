# Optimal card guesses with only yes-or-no feedback

**Open problem.** A shuffled deck contains two copies of each of n labels. Before each card, you guess its label and learn only whether you were right. Find the exact maximum expected number of correct guesses, P⁺_{2,n}, for every n from 11 through 16.

**Status.** Diaconis, Graham and Spiro’s table reports values through n=10 to four decimal places. Luo’s cited paper gives an exact recursion and asks about the large-n limit. The status-search URL was unavailable, so this check does not establish novelty of the proposed larger finite values. [Status source](<https://export.arxiv.org/api/query?search_query=abs:%22card%20guessing%22&sortBy=submittedDate&sortOrder=descending&max_results=50>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. Exact values for n = 11..13 are under review in V3R1T4S PR #200. They are unverified submissions, not established values or record bars. This preparation made no new source request.

## The problem

A wrong guess does not reveal the actual label. With three or more labels, it rules out one possibility while leaving several others. A sufficient state (r,f) records each label’s undetermined multiplicity r_i and the number f_i of earlier positions that forbid it. C(r,f) counts compatible arrangements using the cited inclusion–exclusion formula. Adaptive play chooses a guess using this restricted information, not the hidden deck.

## Backstory

- 1981: Diaconis and Graham solved the single-copy case.
- 2022: Diaconis, Graham and Spiro published the cited small-deck values; related work established asymptotic bounds.
- 2026-09-14: Luo posed the fixed-multiplicity limit question and provided the recursion used here.

## Why it matters

An observation that only says “wrong” still changes future decisions. This makes the game a compact example of inference and control with incomplete feedback, relevant to the reasoning behind card-counting strategies.

## Real-world uses

Exact values can compare guessing heuristics and benchmark belief-state dynamic programs. They also provide finite data for the separate conjecture about the limiting score.

## How to think about it

A greedy guess need not be optimal because feedback changes the future state. Labels can be exchanged, allowing canonical states formed by sorting the (r_i,f_i) pairs. The main challenge is the number of such states and the growth of exact integers.

## What counts as a solution

Give reduced rational values for all n=11,…,16 and a complete reachable-state Bellman table. Using Luo’s notation, independently check p_i=C(r−e_i,f)/C(r,f) and V⁺(r,f)=max_i{p_i[1+V⁺(r−e_i,f)]+(1−p_i)V⁺(r,f+e_i)}, with value zero when no free position remains. Check the initial state r=(2,…,2), f=0, and reproduce n=2,…,10 within one unit of the last printed digit (0.0001 for the four-decimal table). The n=11,…,13 portion is a partial target with an under-review submission in PR #200; no submitted values are established here. Verify state counts from the source formula on tiny decks and compare any newer published values before claiming.

## Our approach

Build exact compatible-deck counts and process canonical belief states by remaining length. Independently check each Bellman equation and the complete requested sequence range.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://arxiv.org/abs/2012.04019>
- <https://arxiv.org/pdf/2012.04019>
- <https://arxiv.org/abs/2010.05059>
- <https://arxiv.org/pdf/2010.05059>
- <https://arxiv.org/abs/2609.25062>
- <https://arxiv.org/pdf/2609.25062>
- Status source: <https://arxiv.org/search/?query=card+guessing+feedback&searchtype=all&abstracts=show&order=-announced_date_first&size=25> — HTTP 429; not retrieved.
- Repository status update supplied for this preparation: <https://github.com/elder-plinius/V3R1T4S/pull/200>.
- Original proposal status source: <https://export.arxiv.org/api/query?search_query=abs:%22card%20guessing%22&sortBy=submittedDate&sortOrder=descending&max_results=50> — no new retrieval in this preparation.
