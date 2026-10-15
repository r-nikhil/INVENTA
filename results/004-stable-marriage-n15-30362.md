# 004 · 30,362 stable matchings in a 15×15 marriage market

**Result.** An explicit stable-marriage instance with 15 people on each side that has exactly **30,362** stable
matchings. The best published instance of that size has **27,059** (Ong et al., 2025, in the instance file of OEIS
[A357271](https://oeis.org/A357271)); our own earlier submission ([discovery 001](001-stable-marriage-n15.md)) had
27,510. So **f(15) ≥ 30,362** (+12.2 % over the published record).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by a
second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #151](https://github.com/elder-plinius/V3R1T4S/pull/151). It supersedes the value in
[draft PR #144](https://github.com/elder-plinius/V3R1T4S/pull/144), which stays open unchanged (the kit never edits an
open submission; a better result is a new one).

---

## The problem

The maximum number of stable matchings *f(n)* in a market of *n* men and *n* women — see
[discovery 001](001-stable-marriage-n15.md) for the problem, its sixty-year history and why it matters.

## What we found

The same exact counter as in [003](003-stable-marriage-n13.md) (rotation-poset ideals, every new best re-checked against
the definition) drove a longer search: several independent iterated-local-search "books" with different random seeds,
re-seeded from the best every 15–50 minutes. Starting from the published 27,059 instance they passed 27,510 (our
discovery 001), 28,549, 29,726, 30,043 and reached **30,362** after about 4 million exact evaluations; 2 million more found
nothing better.

**Checks it passed.** Several exact counters inside the run; three independent skeptic agents in fresh contexts plus the
kit's honesty gate and package checker; and a blind cross-review by OpenAI Codex, which wrote two counters of its own from
the definition, reproduced the published 27,059 first, and then found the identical complete set of 30,362 matchings with
both.

## What it is not

- Not the exact maximum *f(15)* — only a better lower bound; the steady climb suggests more is possible.
- Found by search; no structural explanation is claimed.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-ed514711](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-ed514711/known-knowns/stable-marriage-max-stable-matchings/2026-10-15-r-nikhil-ed514711)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

Instance sha256: `ed5147118033557c8331a5b2b9ec7b08ee67139ee00f417b951f58ac24983fef`.

## Credits

As in [001](001-stable-marriage-n15.md#credits); in particular Ong, Ang, Ho, Eilers, Marks and Buzi, whose 27,059
instance the search started from, and Dan Eilers (OEIS A357269 / A357271).
