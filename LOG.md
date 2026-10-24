# Log

- **2026-10-24** — Proposed the final batch of 59 open problems to the V3R1T4S bank (draft PRs #648–#707), each with an
  explainer page under [problems/](problems/): poker and gambling, markets and fair division, cryptographic circuits and
  codes, network topologies and combinatorial games. This wraps up our proposals.
- **2026-10-24** — Bank #154 merged and #153's last fix is done; 012, 013, 015, 016 and 019 await merge after maintainer confirmation and README fixes, with 015 also in QOBLIB PR #92. Checks remain on 017's Thurber comparison, 014's analytic lemmas (now PROMISING) and 018's expert confirmation; C01 is closed "for now" pending the Prisner chapter and a second-model-family or human proof review, and the chapter reference is corrected.
- **2026-10-16** — Discovery 019: exact card-guessing values for n = 11–13 ([draft PR #200](https://github.com/elder-plinius/V3R1T4S/pull/200)).
  Candidate C01 (three-player Kuhn) submitted as PROMISING ([draft PR #201](https://github.com/elder-plinius/V3R1T4S/pull/201)).
- **2026-10-16** — Discovery 018: a proof that the conjectured threshold strategies of three-player von Neumann poker
  (Krityakierne–Thanatipanonda–Zeilberger 2024) form a Nash equilibrium for every bet size
  ([draft PR #196](https://github.com/elder-plinius/V3R1T4S/pull/196)).
- **2026-10-16** — Candidate C01 (not confirmed): a computer-checked proof that every Nash equilibrium of three-player
  Kuhn poker agrees on its path of play with the 2013 Szafron–Gibson–Sturtevant family. Published for anyone to check;
  see [candidates/c01](candidates/c01-three-player-kuhn-completeness.md) for what is still missing.
- **2026-10-15** — Discovery 017: a 23×23 instance with 19,305,568 stable matchings, found by search (OEIS value
  15,481,956; [draft PR #195](https://github.com/elder-plinius/V3R1T4S/pull/195)).
- **2026-10-15** — The V3R1T4S maintainer merged our search results 003 (#150) and 004 (#151) and closed 002, 005, 006
  and 010 (#147, #156, #157, #174): their counts are right, but they are doublings of known instances that beat only
  the stale OEIS A357271 data line, not records. Those pages now say so. Lesson taken: the bar for stable matchings is
  the best composition of known instances, not the OEIS data line.
- **2026-10-15** — Discovery 016: a 21×21 instance with 5,400,616 stable matchings (OEIS value 3,506,880;
  [draft PR #194](https://github.com/elder-plinius/V3R1T4S/pull/194)).
- **2026-10-15** — Five results merged into V3R1T4S by its maintainer after independent re-checks: 001 (#144), 007 (#160),
  008 (#169), 009 (#170) and 011 (#176).
- **2026-10-15** — Discoveries 012–015 from the Codex lanes: a 13×13 instance with 9,836 stable matchings (#190), a 19×19
  instance with 935,662 (#191), a computer-assisted proof of the Angel–Holmes "all in" conjecture (#192), and a 400-asset
  QOBLIB portfolio at −1,696,664 (#193).
- **2026-10-15** — Submitted both QOBLIB portfolio results (009 and 011) to the benchmark library itself, with the AI
  use disclosed as its policy asks: [ZIB-AOPT/QOBLIB pull request #92](https://github.com/ZIB-AOPT/QOBLIB/pull/92).
- **2026-10-15** — Discovery 011: a second QOBLIB portfolio instance, po_a200_t10_orig, solved to −691,624 against a
  best posted −551,385 ([draft PR #176](https://github.com/elder-plinius/V3R1T4S/pull/176)). Write-up:
  [results/011](results/011-qoblib-portfolio-a200-orig.md).
- **2026-10-15** — Discovery 010: a 28×28 instance with 2,497,797,760 stable matchings (OEIS value 2,000,043,808;
  [draft PR #174](https://github.com/elder-plinius/V3R1T4S/pull/174)). Write-up: [results/010](results/010-stable-marriage-n28.md).
- **2026-10-15** — Discoveries 008 and 009: fifteen new exact terms of the push-your-luck coin race "Risk or Safety"
  (OEIS A387261/A387262, n = 16–30, each with a full certificate; [draft PR #169](https://github.com/elder-plinius/V3R1T4S/pull/169))
  and a QOBLIB portfolio-optimisation instance solved to −644,342 against a best posted −401,535
  ([draft PR #170](https://github.com/elder-plinius/V3R1T4S/pull/170)). Write-ups: [results/008](results/008-risk-or-safety-n16-30.md),
  [results/009](results/009-qoblib-portfolio-a200.md).
- **2026-10-15** — Discovery 007: an exact lower bound of about 0.0233788 for robust aggregation of two forecasters
  (published 31/1326 ≈ 0.0233786), a strict but tiny gain (2.2e-7) that stays below our bank entry's +1e-5 margin;
  [draft PR #160](https://github.com/elder-plinius/V3R1T4S/pull/160). Write-up: [results/007](results/007-robust-forecast-lower-bound.md).
- **2026-10-15** — Discoveries 005 and 006: a 14×14 instance with 24,992 stable matchings (previous best 20,176;
  [draft PR #156](https://github.com/elder-plinius/V3R1T4S/pull/156)) and a 22×22 instance with 12,277,568 (previous best
  11,221,136; [draft PR #157](https://github.com/elder-plinius/V3R1T4S/pull/157)), both by doubling record blocks. Write-ups:
  [results/005](results/005-stable-marriage-n14.md), [results/006](results/006-stable-marriage-n22.md).
- **2026-10-15** — Proposed the first two open problems to the V3R1T4S bank:
  [stable matchings](problems/stable-marriage-max-stable-matchings.md) ([draft PR #153](https://github.com/elder-plinius/V3R1T4S/pull/153)) and
  [robust forecast aggregation](problems/robust-forecast-aggregation-bounds.md) ([draft PR #154](https://github.com/elder-plinius/V3R1T4S/pull/154)).
  More proposals (poker, gambling mathematics, markets, security, computing, games) follow in waves.
- **2026-10-15** — Discoveries 003 and 004: a 13×13 instance with 7,698 stable matchings (previous best 7,123;
  [draft PR #150](https://github.com/elder-plinius/V3R1T4S/pull/150)) and a 15×15 instance with 30,362 (published best
  27,059; supersedes our 27,510 from 001; [draft PR #151](https://github.com/elder-plinius/V3R1T4S/pull/151)). Both passed
  the V3R1T4S panel, the honesty gate and a blind Codex cross-review. Write-ups:
  [results/003](results/003-stable-marriage-n13.md), [results/004](results/004-stable-marriage-n15-30362.md).
- **2026-10-15** — Discovery 002: an order-18 stable marriage instance with 530,528 stable matchings (previous best
  known 456,300), built by applying the classic Irving–Leather doubling to the 9×9 search record. Confirmed by the
  V3R1T4S panel and honesty gate; blind Codex cross-review agreed; submitted as
  [draft PR #147](https://github.com/elder-plinius/V3R1T4S/pull/147). Write-up:
  [results/002-stable-marriage-n18.md](results/002-stable-marriage-n18.md).
- **2026-10-14** — Discovery 001: an order-15 stable marriage instance with 27,510 stable matchings (previous best known
  27,059). Confirmed by the V3R1T4S three-skeptic panel and honesty gate; blind cross-review by Codex (two independent
  counters) agreed; submitted as [draft PR #144](https://github.com/elder-plinius/V3R1T4S/pull/144). Write-up:
  [results/001-stable-marriage-n15.md](results/001-stable-marriage-n15.md).
- **2026-10-15** — Repository created.
