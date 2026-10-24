# INVENTA

**Things found.** Open problems attacked by autonomous Claude research agents, every result checked by skeptics and
reproducible by anyone in seconds. Each discovery gets one plain-language write-up: what the problem is, where it came
from, why it matters, what we found, and how you can verify it yourself.

> *Inventa* (Latin): "things discovered". A companion to [V3R1T4S](https://github.com/elder-plinius/V3R1T4S), the open
> research kit our agents run on, where every result is also submitted for independent review.

## Results

| # | Date | Problem | Result | Status | Verify |
|---|---|---|---|---|---|
| 001 | 2026-10-14 | [Most stable matchings in a 15×15 marriage market](results/001-stable-marriage-n15.md) | 27,510 stable matchings (previous best known: 27,059) | Merged into V3R1T4S ([#144](https://github.com/elder-plinius/V3R1T4S/pull/144)) | ~15 s, Python only |
| 002 | 2026-10-15 | [Most stable matchings in an 18×18 marriage market](results/002-stable-marriage-n18.md) | 530,528 stable matchings (previous best known: 456,300) | Closed by the maintainer: a doubling of known instances, not a record ([#147](https://github.com/elder-plinius/V3R1T4S/pull/147)) | ~5 s, C compiler |
| 003 | 2026-10-15 | [Most stable matchings in a 13×13 marriage market](results/003-stable-marriage-n13.md) | 7,698 stable matchings (previous best known: 7,123) | Merged into V3R1T4S ([#150](https://github.com/elder-plinius/V3R1T4S/pull/150)) | seconds, C compiler |
| 004 | 2026-10-15 | [Most stable matchings in a 15×15 marriage market, improved](results/004-stable-marriage-n15-30362.md) | 30,362 stable matchings (published best: 27,059; our 001: 27,510) | Merged into V3R1T4S ([#151](https://github.com/elder-plinius/V3R1T4S/pull/151)) | seconds, C compiler |
| 005 | 2026-10-15 | [Most stable matchings in a 14×14 marriage market](results/005-stable-marriage-n14.md) | 24,992 stable matchings (previous best known: 20,176) | Closed by the maintainer: a doubling of known instances, not a record ([#156](https://github.com/elder-plinius/V3R1T4S/pull/156)) | seconds, C compiler |
| 006 | 2026-10-15 | [Most stable matchings in a 22×22 marriage market](results/006-stable-marriage-n22.md) | 12,277,568 stable matchings (previous best known: 11,221,136) | Closed by the maintainer: a doubling of known instances, not a record ([#157](https://github.com/elder-plinius/V3R1T4S/pull/157)) | seconds, C compiler |
| 007 | 2026-10-15 | [A slightly higher floor for combining two forecasters](results/007-robust-forecast-lower-bound.md) | Exact lower bound ≈ 0.0233788 on the minimax regret (published: 31/1326 ≈ 0.0233786; tiny, below the bank margin) | Merged into V3R1T4S ([#160](https://github.com/elder-plinius/V3R1T4S/pull/160)) | `sh verify-it-yourself/run_checks.sh` |
| 008 | 2026-10-15 | [Exact optimal-play odds in "Risk or Safety", 16 to 30 points](results/008-risk-or-safety-n16-30.md) | 15 new exact terms of OEIS A387261/A387262 (n = 16–30), each with a full certificate | Merged into V3R1T4S ([#169](https://github.com/elder-plinius/V3R1T4S/pull/169)) | `sh verify-it-yourself/run_checks.sh` |
| 009 | 2026-10-15 | [A better portfolio for a quantum-optimisation benchmark](results/009-qoblib-portfolio-a200.md) | QOBLIB po_a200_t10_s00 (B = 50, λ = 0.01): objective −644,342 (best posted: −401,535) | Merged into V3R1T4S ([#170](https://github.com/elder-plinius/V3R1T4S/pull/170)) | `sh verify-it-yourself/run_checks.sh` |
| 010 | 2026-10-15 | [Most stable matchings in a 28×28 marriage market](results/010-stable-marriage-n28.md) | 2,497,797,760 stable matchings (OEIS value: 2,000,043,808; doubled published 7×7: 2,369,365,120) | Closed by the maintainer: a doubling of known instances, not a record ([#174](https://github.com/elder-plinius/V3R1T4S/pull/174)) | `sh verify-it-yourself/run_checks.sh` |
| 011 | 2026-10-15 | [A better portfolio for a second quantum-optimisation benchmark instance](results/011-qoblib-portfolio-a200-orig.md) | QOBLIB po_a200_t10_orig (B = 50, λ = 0.01): objective −691,624 (best posted: −551,385) | Merged into V3R1T4S ([#176](https://github.com/elder-plinius/V3R1T4S/pull/176)) | `sh verify-it-yourself/run_checks.sh` |
| 012 | 2026-10-15 | [Most stable matchings in a 13×13 marriage market, improved again](results/012-stable-marriage-n13-9836.md) | 9,836 stable matchings (published best: 7,123; our 003: 7,698) | Independently confirmed by the maintainer; small README fixes requested and done on 2026-10-24; merge expected ([PR #190](https://github.com/elder-plinius/V3R1T4S/pull/190)) | `sh verify-it-yourself/run_checks.sh` |
| 013 | 2026-10-15 | [Most stable matchings in a 19×19 marriage market](results/013-stable-marriage-n19.md) | 935,662 stable matchings (OEIS value: 637,336) | Independently confirmed by the maintainer; small README fixes requested and done on 2026-10-24; merge expected ([PR #191](https://github.com/elder-plinius/V3R1T4S/pull/191)) | `sh verify-it-yourself/run_checks.sh` |
| 014 | 2026-10-15 | [He–Holmes Conjecture 9 (attributed to Angel–Holmes)](results/014-angel-holmes-all-in-conjecture.md) | A short stack is always worse off than a tied one: f(x,y,z) − f(y,y,z) ≥ 379/1,813,985,280 (He–Holmes Conjecture 9) | Closed upstream on 2026-10-24 without merging: V3R1T4S records only machine-checkable results, and a proof needs peer review. The maintainer's own checker reproduced every certificate bound ([PR #192](https://github.com/elder-plinius/V3R1T4S/pull/192)) | `sh verify-it-yourself/run_checks.sh` |
| 015 | 2026-10-15 | [A better portfolio for a 400-asset quantum-optimisation benchmark instance](results/015-qoblib-portfolio-a400.md) | QOBLIB po_a400_t10_s00 (B = 100, λ = 0.01): objective −1,696,664 (best public: −1,090,282) | Independently confirmed by the maintainer; small README fixes requested and done on 2026-10-24; merge expected ([PR #193](https://github.com/elder-plinius/V3R1T4S/pull/193)); cell also added to [QOBLIB PR #92](https://github.com/ZIB-AOPT/QOBLIB/pull/92) | `sh verify-it-yourself/run_checks.sh` |
| 016 | 2026-10-15 | [Most stable matchings in a 21×21 marriage market](results/016-stable-marriage-n21.md) | 5,400,616 stable matchings (OEIS value: 3,506,880) | Independently confirmed by the maintainer; small README fixes requested and done on 2026-10-24; merge expected ([PR #194](https://github.com/elder-plinius/V3R1T4S/pull/194)) | `sh verify-it-yourself/run_checks.sh` |
| 017 | 2026-10-15 | [Most stable matchings in a 23×23 marriage market](results/017-stable-marriage-n23.md) | 19,305,568 stable matchings (OEIS value: 15,481,956) | Count confirmed by the maintainer; checking whether Thurber's (2002) odd-size composition with today's blocks could reach about 18.5 million ([PR #195](https://github.com/elder-plinius/V3R1T4S/pull/195)) | `sh verify-it-yourself/run_checks.sh` |
| 018 | 2026-10-16 | [Three-player von Neumann poker: the conjectured strategy is an equilibrium for every bet size](results/018-three-player-von-neumann-poker.md) | Proof for all b > 0 that the threshold profile of Krityakierne–Thanatipanonda–Zeilberger (2024) is a Nash equilibrium | Closed upstream on 2026-10-24 without merging: V3R1T4S records only machine-checkable results, and a proof needs peer review. The maintainer reproduced the closed forms and the b = 2 value to 60 digits ([PR #196](https://github.com/elder-plinius/V3R1T4S/pull/196)) | `sh verify-it-yourself/run_checks.sh` |
| 019 | 2026-10-16 | [Exact optimal scores in card guessing with yes/no feedback, n = 11–13](results/019-card-guessing-n11-13.md) | Exact values for two-copy decks of 11, 12 and 13 labels (published values stop at n = 10) | Independently confirmed by the maintainer; small README fixes requested and done on 2026-10-24; merge expected ([PR #200](https://github.com/elder-plinius/V3R1T4S/pull/200)) | `sh verify-it-yourself/run_checks.sh` |


## Candidates (not confirmed)

Results that passed part of the gauntlet but not all of it. They are published so that anyone can check them and must
not be cited as confirmed.

| # | Date | Problem | Candidate result | What is missing |
|---|---|---|---|---|
| C01 | 2026-10-16 | [Three-player Kuhn poker: are all Nash equilibria in the 2013 family?](candidates/c01-three-player-kuhn-completeness.md) | A computer-checked proof that every Nash equilibrium agrees on its path of play with the Szafron–Gibson–Sturtevant family | Closed by the maintainer on 2026-10-17 "for now" ([PR #201](https://github.com/elder-plinius/V3R1T4S/pull/201)); refile once Prisner's (2014) chapter "Example: VNM POKER and KUHN POKER" has been read and the proof has had a second-model-family or human review |

## Problems we proposed

Open problems we submitted to the [V3R1T4S bank](https://github.com/elder-plinius/V3R1T4S/tree/main/bank) so that anyone
can attack them. Each has a page: what it is, where it came from, why it matters, how to think about it and what would
count as a solution.

| Problem | Area | Bank proposal | Our results |
|---|---|---|---|
| [How many stable matchings can a marriage market have?](problems/stable-marriage-max-stable-matchings.md) | Market design, combinatorics | Open; last requested fix done ([PR #153](https://github.com/elder-plinius/V3R1T4S/pull/153)) | 001–006, 010, 012, 013, 016, 017 |
| [Robust forecast aggregation](problems/robust-forecast-aggregation-bounds.md) | Forecasting, prediction markets | Merged into the bank's proposed list on 2026-10-16 ([PR #154](https://github.com/elder-plinius/V3R1T4S/pull/154)) | 007 (tiny lower-bound gain) |
| [Does matching a rival’s stack reduce first-bust risk?](problems/all-in-three-player-ruin-angel-holmes-conjecture.md) | Games, poker, combinatorics | [draft PR #648](https://github.com/elder-plinius/V3R1T4S/pull/648) | [014](results/014-angel-holmes-all-in-conjecture.md) (under review) |
| [Does alternating predictive regret matching converge?](problems/alternating-prm-plus-ergodic-convergence.md) | Algorithms, circuits | [draft PR #649](https://github.com/elder-plinius/V3R1T4S/pull/649) | — |
| [Settle an unresolved antichess opening](problems/antichess-open-first-moves.md) | Games, poker, combinatorics | [draft PR #650](https://github.com/elder-plinius/V3R1T4S/pull/650) | — |
| [When does a two-item auction become deterministic?](problems/auction-deterministic-threshold-monotonicity.md) | Algorithms, circuits | [draft PR #652](https://github.com/elder-plinius/V3R1T4S/pull/652) | — |
| [Can two Beggar-My-Neighbour histories merge before ending?](problems/beggar-terminating-trajectory-collision.md) | Games, poker, combinatorics | [draft PR #653](https://github.com/elder-plinius/V3R1T4S/pull/653) | — |
| [When both sides’ best offers trade too little](problems/bilateral-trade-best-offer-vs-second-best.md) | Games, poker, combinatorics | [draft PR #654](https://github.com/elder-plinius/V3R1T4S/pull/654) | — |
| [How many equilibria can binary choices create?](problems/binary-action-games-max-nash-equilibria.md) | Games, poker, combinatorics | [draft PR #655](https://github.com/elder-plinius/V3R1T4S/pull/655) | — |
| [A seventh binary-coefficient APN class in dimension eleven](problems/binary-coefficient-apn-dimension-11.md) | Records and constructions | [draft PR #656](https://github.com/elder-plinius/V3R1T4S/pull/656) | — |
| [Shorter binary minimal codes for dimensions ten to thirteen](problems/binary-minimal-code-length-records.md) | Records and constructions | [draft PR #657](https://github.com/elder-plinius/V3R1T4S/pull/657) | — |
| [Smaller circuits for binary polynomial multiplication](problems/binary-polynomial-multiplication-gates.md) | Algorithms, circuits | [draft PR #658](https://github.com/elder-plinius/V3R1T4S/pull/658) | — |
| [A certified ceiling on selfish-mining revenue](problems/bitcoin-selfish-mining-revenue-bounds.md) | Games, poker, combinatorics | [draft PR #659](https://github.com/elder-plinius/V3R1T4S/pull/659) | — |
| [Optimal card guesses with only yes-or-no feedback](problems/card-guessing-yes-no-feedback-exact.md) | Games, poker, combinatorics | [draft PR #660](https://github.com/elder-plinius/V3R1T4S/pull/660) | [019](results/019-card-guessing-n11-13.md) (under review) |
| [The fair margin in “Fill your basket”](problems/coin-basket-adversarial-games.md) | Games, poker, combinatorics | [draft PR #661](https://github.com/elder-plinius/V3R1T4S/pull/661) | — |
| [Optimal coin placement into randomly chosen baskets](problems/coin-basket-random-expected-values.md) | Games, poker, combinatorics | [draft PR #662](https://github.com/elder-plinius/V3R1T4S/pull/662) | — |
| [Cover every outcome with fewer codewords](problems/covering-codes-q2-q4-upper-bounds.md) | Records and constructions | [draft PR #663](https://github.com/elder-plinius/V3R1T4S/pull/663) | — |
| [Shorter chains for elliptic-curve inversion](problems/ecc-inversion-addition-chains.md) | Algorithms, circuits | [draft PR #664](https://github.com/elder-plinius/V3R1T4S/pull/664) | — |
| [Can four people always divide goods with EFX fairness?](problems/four-agent-additive-goods-efx-obstruction.md) | Games, poker, combinatorics | [draft PR #665](https://github.com/elder-plinius/V3R1T4S/pull/665) | — |
| [Does scaling every stack preserve elimination odds?](problems/gamblers-ruin-scaling-conjecture.md) | Games, poker, combinatorics | [draft PR #666](https://github.com/elder-plinius/V3R1T4S/pull/666) | — |
| [Multiply eight-term binary polynomials with 25 products](problems/gf2-polymult-8term-25-products.md) | Algorithms, circuits | [draft PR #667](https://github.com/elder-plinius/V3R1T4S/pull/667) | — |
| [Better graphs for short network paths](problems/graph-golf-order-degree-aspl.md) | Games, poker, combinatorics | [draft PR #668](https://github.com/elder-plinius/V3R1T4S/pull/668) | — |
| [Can stable ad-slot bids waste more welfare?](problems/gsp-pure-nash-poa-conjecture.md) | Games, poker, combinatorics | [draft PR #669](https://github.com/elder-plinius/V3R1T4S/pull/669) | — |
| [What is the value of four-player continuous Guts?](problems/guts-four-player-synchronous-value.md) | Games, poker, combinatorics | [draft PR #670](https://github.com/elder-plinius/V3R1T4S/pull/670) | — |
| [Can an independent Guts coalition force a loss?](problems/guts-n-player-asynchronous-coalition.md) | Games, poker, combinatorics | [draft PR #671](https://github.com/elder-plinius/V3R1T4S/pull/671) | — |
| [Does the Weenie rule protect the symmetric Guts threshold?](problems/guts-weenie-rule-strong-equilibrium.md) | Games, poker, combinatorics | [draft PR #672](https://github.com/elder-plinius/V3R1T4S/pull/672) | — |
| [Exact values for hidden-information game benchmarks](problems/iig-benchmark-exact-nash-values.md) | Games, poker, combinatorics | [draft PR #673](https://github.com/elder-plinius/V3R1T4S/pull/673) | — |
| [Can two small constrained allocations unlock four-agent fairness?](problems/laminar-ef1-four-agent-key-matroids.md) | Games, poker, combinatorics | [draft PR #674](https://github.com/elder-plinius/V3R1T4S/pull/674) | — |
| [Coordinate more players in Levine’s hat puzzle](problems/levine-hat-n-player-records.md) | Games, poker, combinatorics | [draft PR #675](https://github.com/elder-plinius/V3R1T4S/pull/675) | — |
| [Close the gap in the two-player hat puzzle](problems/levine-hat-two-player-value.md) | Games, poker, combinatorics | [draft PR #676](https://github.com/elder-plinius/V3R1T4S/pull/676) | — |
| [The fewest tickets guaranteeing a two-number match](problems/lottery-numbers-l-n-6-6-2-beyond-70.md) | Records and constructions | [draft PR #677](https://github.com/elder-plinius/V3R1T4S/pull/677) | — |
| [Smaller exact median selection networks](problems/median-selection-network-size-records.md) | Records and constructions | [draft PR #678](https://github.com/elder-plinius/V3R1T4S/pull/678) | — |
| [Sparse five-round broadcast graphs on 23–25 vertices](problems/minimum-broadcast-graphs-23-25.md) | Games, poker, combinatorics | [draft PR #679](https://github.com/elder-plinius/V3R1T4S/pull/679) | — |
| [Close a gap in financial optimization benchmarks](problems/minlplib-finance-open-instances.md) | Optimisation benchmarks | [draft PR #680](https://github.com/elder-plinius/V3R1T4S/pull/680) | — |
| [Who wins misère Sprouts from 21 spots?](problems/misere-sprouts-21-spots.md) | Games, poker, combinatorics | [draft PR #681](https://github.com/elder-plinius/V3R1T4S/pull/681) | — |
| [The revenue cost of one reserve for everyone](problems/myerson-vs-anonymous-reserve-gap.md) | Games, poker, combinatorics | [draft PR #682](https://github.com/elder-plinius/V3R1T4S/pull/682) | — |
| [Smaller verified circuits for AES components](problems/nist-aes-circuit-records.md) | Algorithms, circuits | [draft PR #683](https://github.com/elder-plinius/V3R1T4S/pull/683) | — |
| [Solve the next NoGo boards](problems/nogo-28-point-boards.md) | Games, poker, combinatorics | [draft PR #684](https://github.com/elder-plinius/V3R1T4S/pull/684) | — |
| [Fewer AND gates for five small power S-boxes](problems/non-aes-power-sbox-and-records.md) | Records and constructions | [draft PR #685](https://github.com/elder-plinius/V3R1T4S/pull/685) | — |
| [Find a provable repeating pattern in an octal game](problems/octal-games-unsettled-periodicity.md) | Games, poker, combinatorics | [draft PR #686](https://github.com/elder-plinius/V3R1T4S/pull/686) | — |
| [Higher unrestricted Boolean nonlinearity in odd dimensions](problems/odd-boolean-nonlinearity-9-11-13.md) | Records and constructions | [draft PR #687](https://github.com/elder-plinius/V3R1T4S/pull/687) | — |
| [Can rotating a permutation always win Penney’s game?](problems/penney-permutations-rotation-conjecture.md) | Games, poker, combinatorics | [draft PR #688](https://github.com/elder-plinius/V3R1T4S/pull/688) | — |
| [Smaller exact Birkhoff decompositions for two QOBLIB matrices](problems/qoblib-birkhoff-small-exact-records.md) | Optimisation benchmarks | [draft PR #689](https://github.com/elder-plinius/V3R1T4S/pull/689) | — |
| [Certify the exact optimum of a small QOBLIB portfolio instance](problems/qoblib-portfolio-ten-assets-exact.md) | Optimisation benchmarks | [draft PR #690](https://github.com/elder-plinius/V3R1T4S/pull/690) | — |
| [Can fair assignment lotteries always be coupled fairly?](problems/random-assignment-dec-ef-conjecture.md) | Games, poker, combinatorics | [draft PR #691](https://github.com/elder-plinius/V3R1T4S/pull/691) | — |
| [Exact odds for a push-your-luck coin race](problems/risk-or-safety-exact-optimal-play.md) | Games, poker, combinatorics | [draft PR #692](https://github.com/elder-plinius/V3R1T4S/pull/692) | [008](results/008-risk-or-safety-n16-30.md) (merged) |
| [A first certified answer for an unknown SAT instance](problems/sat-competition-2026-unknown-first-solve.md) | Optimisation benchmarks | [draft PR #693](https://github.com/elder-plinius/V3R1T4S/pull/693) | — |
| [Can smaller tournament sets support unfair dice games?](problems/schutte-multiple-tournament-dice-bounds.md) | Games, poker, combinatorics | [draft PR #694](https://github.com/elder-plinius/V3R1T4S/pull/694) | — |
| [Selecting a median with fewer comparisons](problems/selection-min-comparisons-n16-n17.md) | Algorithms, circuits | [draft PR #695](https://github.com/elder-plinius/V3R1T4S/pull/695) | — |
| [How costly can the best stable shared network be?](problems/shapley-network-design-pos-three-players.md) | Games, poker, combinatorics | [draft PR #696](https://github.com/elder-plinius/V3R1T4S/pull/696) | — |
| [Larger short binary codes correcting two or three deletions](problems/short-binary-multiple-deletion-code-records.md) | Records and constructions | [draft PR #697](https://github.com/elder-plinius/V3R1T4S/pull/697) | — |
| [Exact certificates for eight SMT-COMP P4/DFA holdouts](problems/smt2026-p4-dfa-unknown-certificates.md) | Optimisation benchmarks | [draft PR #698](https://github.com/elder-plinius/V3R1T4S/pull/698) | — |
| [The longest repeating subtraction game](problems/subtraction-game-max-period-terms.md) | Games, poker, combinatorics | [draft PR #699](https://github.com/elder-plinius/V3R1T4S/pull/699) | — |
| [Meet sooner without a shared direction](problems/symmetric-rendezvous-records.md) | Games, poker, combinatorics | [draft PR #700](https://github.com/elder-plinius/V3R1T4S/pull/700) | — |
| [Can three people always divide chores with EFX fairness?](problems/three-agent-additive-chores-efx.md) | Games, poker, combinatorics | [draft PR #701](https://github.com/elder-plinius/V3R1T4S/pull/701) | — |
| [A tighter equilibrium for three-player jam-or-fold poker](problems/three-player-jamfold-sng-epsilon.md) | Games, poker, combinatorics | [draft PR #702](https://github.com/elder-plinius/V3R1T4S/pull/702) | — |
| [Are all on-path Kuhn poker equilibria already known?](problems/three-player-kuhn-equilibrium-completeness.md) | Games, poker, combinatorics | [draft PR #703](https://github.com/elder-plinius/V3R1T4S/pull/703) | [C01](candidates/c01-three-player-kuhn-completeness.md) (candidate) |
| [Verify a three-player bluffing equilibrium](problems/three-player-von-neumann-poker-equilibrium.md) | Games, poker, combinatorics | [draft PR #704](https://github.com/elder-plinius/V3R1T4S/pull/704) | [018](results/018-three-player-von-neumann-poker.md) (under review) |
| [Can lottery menus outperform item prices by more?](problems/unit-demand-lottery-vs-item-pricing-gap.md) | Games, poker, combinatorics | [draft PR #705](https://github.com/elder-plinius/V3R1T4S/pull/705) | — |
| [Smaller XOR circuits for the Whirlwind M0 and M1 maps](problems/whirlwind-linear-layer-xor-records.md) | Records and constructions | [draft PR #706](https://github.com/elder-plinius/V3R1T4S/pull/706) | — |
| [More codewords for one-way bit errors](problems/z-channel-single-error-codes.md) | Records and constructions | [draft PR #707](https://github.com/elder-plinius/V3R1T4S/pull/707) | — |

## How a result gets here

1. **Hunt.** Several agent lanes (Claude Opus and Fable models, and OpenAI Codex lanes running the same kit) work through open problems that have a public record
   table or a precise definition, so that any answer is checkable by a stranger's computer.
2. **Gauntlet.** A claim must survive the V3R1T4S kit: a frozen success rule, three independent skeptic agents in fresh
   contexts (reproduce, novelty, criterion), and an honesty gate.
3. **Blind review.** A fresh model context re-derives the result from the definition alone: OpenAI Codex for results from
   Claude lanes (a cross-model check); for results from Codex lanes it is a separate Codex context, and each write-up says so.
4. **Submit.** Only then is it packaged with a self-contained verifier and submitted upstream; it is written up here.

Most runs find nothing; that is expected. Only results that passed every step appear in the table.

## Log

Running updates: [LOG.md](LOG.md).

## Licence

Text: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Objects and verifiers live with each V3R1T4S submission
under that repository's licences.
