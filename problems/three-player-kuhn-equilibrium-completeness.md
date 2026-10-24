# Are all on-path Kuhn poker equilibria already known?

**Open problem.** Three-player Kuhn poker has a known family of equilibrium strategies. Does every Nash equilibrium agree with some member of that family at every information state it actually reaches, or is there an equilibrium with different on-path play?

**Status.** Szafron, Gibson and Sturtevant give the reference equilibrium family. The cited later solver work reports profiles differing at unreachable information states. Such off-path differences alone do not answer the proposal’s on-path completeness question. [Status source](<https://en.wikipedia.org/wiki/Kuhn_poker>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. A candidate proof was closed in V3R1T4S PR #201 pending a novelty check of Prisner (2014), chapter "Example: VNM POKER and KUHN POKER", and an independent review. This does not establish completeness. This preparation made no new source request.

## The problem

Three players each ante one chip and receive distinct cards from {1,2,3,4}; the unused card stays hidden. There is one betting round, a one-chip bet and no raises. Player 1 acts first; players check or bet, then fold or call when facing a bet. A behavioral profile specifies 48 action probabilities. An action after a history with zero probability is off-path; changing only that action can create a different profile without changing observed play. For example, if Player 1 never opens with a bet, a later response to that opening is unreachable during play of that profile.

## Backstory

- 2010: Abou Risk and Szafron introduced the cited three-player game.
- 2013: Szafron, Gibson and Sturtevant derived the parameterized family and asked whether it was complete.
- 2018: Ganzfried, Nowak and Pinales repeated the open question.
- 2026: Ganzfried’s exact-solver work exhibited off-path differences and computed full-game equilibria.

## Why it matters

One equilibrium calculation does not describe every strategically stable way to play. The question asks whether multi-player poker admits genuinely different observable equilibria beyond a familiar analytical family.

## Real-world uses

A completeness certificate would support exhaustive equilibrium benchmarks. A counterexample would expose strategy patterns that solvers or analytical assumptions can miss.

## How to think about it

The family’s payoff vector is (−(1+2β)/48, −1/48, (1+β)/24), with β∈[0,1/4], and Player 1 always checks first. Those properties suggest focused counterexample searches. A candidate must remain unexploitable against full unilateral deviations, including paths it does not normally reach.

## What counts as a solution

Either give 48 rational probabilities and independently verify every player’s exact best-response equality over all 24 deals, plus a proof of on-path nonmembership in every subfamily; or provide a machine-checked proof or independently checked exact certificate of completeness. Useful counterexample witnesses include a different second-player payoff, a payoff vector outside the displayed family, or a positive opening-bet probability. Otherwise compare the reached information states directly with Tables 2–3. Numerical solver tolerances and off-path-only changes do not count. The candidate in closed PR #201 still needs a novelty check against Prisner (2014), chapter “Example: VNM POKER and KUHN POKER”, and independent review. The listed partial targets prove the universal second-player payoff or first-player checking property; they are not established here.

## Our approach

Search equilibrium conditions with explicit witnesses of on-path difference. Independently verify rational candidates and use exact support cases for a possible completeness proof.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <https://webdocs.cs.ualberta.ca/~games/poker/publications/AAMAS13-3pkuhn.pdf>
- <https://en.wikipedia.org/wiki/Kuhn_poker> — HTTP 403; not retrieved.
- <https://arxiv.org/abs/2509.25618>
- <https://arxiv.org/pdf/2509.25618v3>
- <https://arxiv.org/abs/2606.25997>
- <https://arxiv.org/pdf/1804.04789>
- <https://arxiv.org/abs/1802.04670>
- Repository status update supplied for this preparation: <https://github.com/elder-plinius/V3R1T4S/pull/201>.
