# 003 · 7,698 stable matchings in a 13×13 marriage market

**Result.** An explicit stable-marriage instance with 13 people on each side that has exactly **7,698** stable
matchings — more than the best previously known instance of that size (**7,123**, Ong et al., 2025, in the instance file
of OEIS [A357271](https://oeis.org/A357271)). So **f(13) ≥ 7,698** (+8.1 %).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by a
second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #150](https://github.com/elder-plinius/V3R1T4S/pull/150).

---

## The problem

How many stable matchings can a market of *n* men and *n* women have at most? Call it *f(n)*. The problem, its history
and why it matters for real matching markets (residency matching, school choice) are told in
[discovery 001](001-stable-marriage-n15.md). In short: exact values are known only for very small *n*; for larger *n* the
best we have are explicit record instances, and odd sizes are the hardest to build by hand.

## Backstory for n = 13

- Edward Thurber's 2002 compositions gave 6,720 for *n* = 13 (the OEIS A357271 data line).
- In 2024–2025 Ryan Ong, Bethany Ang, Abigail Ho, Dan Eilers, Justin Marks and Genti Buzi raised it to 7,123 by improved
  hill climbing; their instance is published with the OEIS entry.

## What we found

A research lane wrote a fast exact counter (it counts stable matchings as the ideals of the instance's *rotation
poset*, and re-checks every new best with a lattice walk that tests each matching against the definition) and ran an
iterated local search from the published 7,123 instance: random swaps inside one person's ranking, sideways moves
allowed, a random kick when stuck. It reached 7,415 and then **7,698** after about 91,000 exact evaluations (about five
minutes); some 12 million further evaluations found nothing better.

**Checks it passed.** Several exact counters inside the run; three independent skeptic agents in fresh contexts plus the
kit's honesty gate and package checker; and a blind cross-review by OpenAI Codex, which wrote two counters of its own from
the definition, reproduced the published 7,123 first, and then found the identical complete set of 7,698 matchings with
both.

## What it is not

- Not the exact maximum *f(13)* — only a better lower bound.
- Found by search; no structural explanation is claimed.

## Verify it yourself

Submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-ec9b2daf](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-14-r-nikhil-ec9b2daf/known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-ec9b2daf)
— run `sh verify-it-yourself/run_checks.sh` there; the last line should be `PASS`.

Instance sha256: `ec9b2daf4bafd04fb7118987cc88ae424471d1bb49f6e3632fb0367c9e3acc69`.

## Credits

Gale and Shapley; Knuth; Irving and Leather; Gusfield and Irving; Thurber; Ong, Ang, Ho, Eilers, Marks and Buzi (the
7,123 instance this search started from); Dan Eilers (OEIS A357269 / A357271); the V3R1T4S kit by
[elder-plinius](https://github.com/elder-plinius/V3R1T4S).
