# Larger short binary codes correcting two or three deletions

**Open problem.** Can a length-15 or length-16 binary code beat a listed two- or three-deletion size?

**Status.** Franziska Weindel and Reinhard Heckel, LLM-Guided Search for Deletion-Correcting Codes, arXiv:2504.00613v2 (5 June 2026), Table 2, gives best-known construction sizes and unresolved upper bounds. Maxima across every reported row are (n,s)=(15,2):136, (16,2):215, (15,3):30 and (16,3):42. The LP upper bounds are 277,487,61,99. A binary code corrects s adversarial deletions when distinct codewords have disjoint sets of length n-s subsequences. These unrestricted nonlinear synchronization-error codes differ from upstream Hamming-metric linear, covering and constant-weight codes, and from quaternary edit codes with DNA constraints.

Status checked: 2026-10-15 (supplied literature-status date; primary publication re-read 2026-10-24, later literature not independently rechecked). [Status source](<https://arxiv.org/html/2504.00613>).

## The problem

Deleting s positions leaves a subsequence of length n-s. A code corrects s adversarial deletions only if two different codewords never produce the same received subsequence.

## Backstory

Weindel and Heckel’s June 2026 Table 2 compares constructions, exact optimization and independent-set heuristics. Taking every row’s maximum gives 136,215,30,42 for (15,2),(16,2),(15,3),(16,3). The respective LP upper bounds remain 277,487,61,99.

## Why it matters

Larger codebooks carry more messages at a fixed length while preserving exact synchronization-error correction. Hamming distance is a different condition.

## Real-world uses

Deletion codes are studied for synchronization errors and DNA data storage. Short codes can also serve as inner components of larger constructions.

## How to think about it

Treat codewords as vertices of a conflict graph. Local independent-set exchanges avoid storing every edge. Direct concatenation can fail when deletions cross block boundaries, so any composition needs its own proof.

## What counts as a solution

Provide an explicit set of distinct binary words with respectively at least 137, 216, 31 or 43 codewords for any one of the four specified (n,s) cells, with pairwise disjoint s-deletion subsequence sets. No linearity, constant-weight or decoder-efficiency assumption is imposed. The complete codebook is the certificate. Also strictly improve the best comparable published result at claim time, including compatible compositions of published objects. State whether the candidate is a composition and identify its components. Values in unmerged pull requests do not set the bar.

For every word enumerate all choices of s deleted positions, deduplicate the resulting length n−s strings within that word, and insert each string into a map from received string to originating codeword. Reject if a string occurs for two distinct words. Check word length, alphabet and uniqueness, then compare code size to the frozen threshold. Independently cross-check with pairwise dynamic-programming longest common subsequences: LCS(x,y)<n−s. At these four thresholds fewer than 30000 deletion-pattern evaluations suffice for the smallest winning certificates.

## Our approach

Use implicit conflicts and local trades, then enumerate and deduplicate each word’s deletion subsequences. Compare all published rows and valid later compositions. No larger codebook is claimed here.

## Sources

Primary sources were requested once on 2026-10-24. The source-specific checks and limits are recorded with this preparation.

- <https://arxiv.org/html/2504.00613>
