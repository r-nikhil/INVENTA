# INVENTA

**Things found.** Open problems attacked by autonomous Claude research agents, every result checked by skeptics and
reproducible by anyone in seconds. Each discovery gets one plain-language write-up: what the problem is, where it came
from, why it matters, what we found, and how you can verify it yourself.

> *Inventa* (Latin): "things discovered". A companion to [V3R1T4S](https://github.com/elder-plinius/V3R1T4S), the open
> research kit our agents run on, where every result is also submitted for independent review.

## Results

| # | Date | Problem | Result | Status | Verify |
|---|---|---|---|---|---|
| 001 | 2026-10-14 | [Most stable matchings in a 15×15 marriage market](results/001-stable-marriage-n15.md) | 27,510 stable matchings (previous best known: 27,059) | Submitted ([draft PR #144](https://github.com/elder-plinius/V3R1T4S/pull/144)); superseded by 004 | ~15 s, Python only |
| 002 | 2026-10-15 | [Most stable matchings in an 18×18 marriage market](results/002-stable-marriage-n18.md) | 530,528 stable matchings (previous best known: 456,300) | Submitted to V3R1T4S ([draft PR #147](https://github.com/elder-plinius/V3R1T4S/pull/147)) | ~5 s, C compiler |
| 003 | 2026-10-15 | [Most stable matchings in a 13×13 marriage market](results/003-stable-marriage-n13.md) | 7,698 stable matchings (previous best known: 7,123) | Submitted to V3R1T4S ([draft PR #150](https://github.com/elder-plinius/V3R1T4S/pull/150)) | seconds, C compiler |
| 004 | 2026-10-15 | [Most stable matchings in a 15×15 marriage market, improved](results/004-stable-marriage-n15-30362.md) | 30,362 stable matchings (published best: 27,059; our 001: 27,510) | Submitted to V3R1T4S ([draft PR #151](https://github.com/elder-plinius/V3R1T4S/pull/151)) | seconds, C compiler |
| 005 | 2026-10-15 | [Most stable matchings in a 14×14 marriage market](results/005-stable-marriage-n14.md) | 24,992 stable matchings (previous best known: 20,176) | Submitted to V3R1T4S ([draft PR #156](https://github.com/elder-plinius/V3R1T4S/pull/156)) | seconds, C compiler |
| 006 | 2026-10-15 | [Most stable matchings in a 22×22 marriage market](results/006-stable-marriage-n22.md) | 12,277,568 stable matchings (previous best known: 11,221,136) | Submitted to V3R1T4S ([draft PR #157](https://github.com/elder-plinius/V3R1T4S/pull/157)) | seconds, C compiler |
| 007 | 2026-10-15 | [A slightly higher floor for combining two forecasters](results/007-robust-forecast-lower-bound.md) | Exact lower bound ≈ 0.0233788 on the minimax regret (published: 31/1326 ≈ 0.0233786; tiny, below the bank margin) | Submitted to V3R1T4S ([draft PR #160](https://github.com/elder-plinius/V3R1T4S/pull/160)) | `sh verify-it-yourself/run_checks.sh` |
| 008 | 2026-10-15 | [Exact optimal-play odds in "Risk or Safety", 16 to 30 points](results/008-risk-or-safety-n16-30.md) | 15 new exact terms of OEIS A387261/A387262 (n = 16–30), each with a full certificate | Submitted to V3R1T4S ([draft PR #169](https://github.com/elder-plinius/V3R1T4S/pull/169)) | `sh verify-it-yourself/run_checks.sh` |
| 009 | 2026-10-15 | [A better portfolio for a quantum-optimisation benchmark](results/009-qoblib-portfolio-a200.md) | QOBLIB po_a200_t10_s00 (B = 50, λ = 0.01): objective −644,342 (best posted: −401,535) | Submitted to V3R1T4S ([draft PR #170](https://github.com/elder-plinius/V3R1T4S/pull/170)) | `sh verify-it-yourself/run_checks.sh` |
| 010 | 2026-10-15 | [Most stable matchings in a 28×28 marriage market](results/010-stable-marriage-n28.md) | 2,497,797,760 stable matchings (OEIS value: 2,000,043,808; doubled published 7×7: 2,369,365,120) | Submitted to V3R1T4S ([draft PR #174](https://github.com/elder-plinius/V3R1T4S/pull/174)) | `sh verify-it-yourself/run_checks.sh` |
| 011 | 2026-10-15 | [A better portfolio for a second quantum-optimisation benchmark instance](results/011-qoblib-portfolio-a200-orig.md) | QOBLIB po_a200_t10_orig (B = 50, λ = 0.01): objective −691,624 (best posted: −551,385) | Submitted to V3R1T4S ([draft PR #176](https://github.com/elder-plinius/V3R1T4S/pull/176)) | `sh verify-it-yourself/run_checks.sh` |
| 012 | 2026-10-15 | [Most stable matchings in a 13×13 marriage market, improved again](results/012-stable-marriage-n13-9836.md) | 9,836 stable matchings (published best: 7,123; our 003: 7,698) | Submitted to V3R1T4S ([draft PR #190](https://github.com/elder-plinius/V3R1T4S/pull/190)) | `sh verify-it-yourself/run_checks.sh` |
| 013 | 2026-10-15 | [Most stable matchings in a 19×19 marriage market](results/013-stable-marriage-n19.md) | 935,662 stable matchings (OEIS value: 637,336) | Submitted to V3R1T4S ([draft PR #191](https://github.com/elder-plinius/V3R1T4S/pull/191)) | `sh verify-it-yourself/run_checks.sh` |
| 014 | 2026-10-15 | [Proof of the Angel–Holmes "all in" conjecture](results/014-angel-holmes-all-in-conjecture.md) | A short stack is always worse off than a tied one: f(x,y,z) − f(y,y,z) ≥ 379/1,813,985,280 (He–Holmes Conjecture 9) | Submitted to V3R1T4S ([draft PR #192](https://github.com/elder-plinius/V3R1T4S/pull/192)) | `sh verify-it-yourself/run_checks.sh` |
| 015 | 2026-10-15 | [A better portfolio for a 400-asset quantum-optimisation benchmark instance](results/015-qoblib-portfolio-a400.md) | QOBLIB po_a400_t10_s00 (B = 100, λ = 0.01): objective −1,696,664 (best public: −1,090,282) | Submitted to V3R1T4S ([draft PR #193](https://github.com/elder-plinius/V3R1T4S/pull/193)) | `sh verify-it-yourself/run_checks.sh` |


## Problems we proposed

Open problems we submitted to the [V3R1T4S bank](https://github.com/elder-plinius/V3R1T4S/tree/main/bank) so that anyone
can attack them. Each has a page: what it is, where it came from, why it matters, how to think about it and what would
count as a solution.

| Problem | Area | Bank proposal | Our results |
|---|---|---|---|
| [How many stable matchings can a marriage market have?](problems/stable-marriage-max-stable-matchings.md) | Market design, combinatorics | [draft PR #153](https://github.com/elder-plinius/V3R1T4S/pull/153) | 001–006, 010, 012, 013 |
| [Robust forecast aggregation](problems/robust-forecast-aggregation-bounds.md) | Forecasting, prediction markets | [draft PR #154](https://github.com/elder-plinius/V3R1T4S/pull/154) | 007 (tiny lower-bound gain) |

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
