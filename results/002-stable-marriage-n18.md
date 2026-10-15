# 002 · Doubling a record: 530,528 stable matchings in an 18×18 marriage market

**Result.** An explicit stable-marriage instance with 18 people on each side that has exactly **530,528** stable
matchings — more than the best previously known instance of that size (**456,300**, OEIS
[A357271](https://oeis.org/A357271), from Edward Thurber's 2002 compositions). In other words, **f(18) ≥ 530,528**
(+16.3 %).

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by a
second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #147](https://github.com/elder-plinius/V3R1T4S/pull/147).

---

## The problem

The same question as [discovery 001](001-stable-marriage-n15.md): in a market of *n* men and *n* women who each rank
everyone on the other side, how many **stable** matchings (no pair would rather run off together) can there be at most?
Call it *f(n)*. Exact values are known only for tiny *n*; for larger *n* we have explicit examples (lower bounds) and
upper bounds of the form *cⁿ* that are far apart (constructions grow like about 2.28ⁿ, the best upper bound like 3.55ⁿ).

## Backstory

- **1986 — doubling.** Robert Irving and Paul Leather showed how to take a market of size *k* and build one of size *2k*
  with many more stable matchings. Starting from Donald Knuth's small examples, repeated doubling gives 1, 2, 10, 268 and
  195,472 stable matchings at sizes 1, 2, 4, 8 and 16 (OEIS A005154).
- **2002 — every size.** Edward Thurber combined ("composed") smaller instances to cover every *n*. Most entries of
  OEIS A357271 (best known lower bounds) still come from those compositions, including **456,300** at *n* = 18.
- **2024–2026 — computer search.** Ryan Ong, Bethany Ang, Abigail Ho, Dan Eilers, Justin Marks and Genti Buzi used
  improved hill climbing to find better instances at the odd sizes 7, 9, 11, 13 and 15 — for example 365 stable
  matchings at *n* = 9. Our discovery 001 then pushed *n* = 15 further.

The new odd-size records were found by search, one size at a time. The even sizes in the table were not revisited.

## What we found

A research lane's "constructor" pass noticed that a simple product construction is exactly the Irving–Leather
doubling. Replace every person of a market *O* by a couple from Knuth's 2×2 market (which has 2 stable matchings):
men rank women first by their *O*-rank and then by the inner rank; women do the same with the inner order reversed.
Applied to Knuth's 4×4 market this reproduces the classic 268 (size 8) and 195,472 (size 16) — a check that the product
really is the doubling.

Nobody had applied it to the new search records. Applied to the 9×9 record instance with 365 stable matchings, it gives
an 18×18 instance with **530,528** stable matchings, beating the table's 456,300.

**Checks it passed.**
1. Four exact counters inside the run (a rotation-poset dynamic program, a lattice walk and a reverse search that each
   re-check every matching, and a Python lattice walk), all giving 530,528. The success rule (strict improvement; the
   counters must agree) was frozen before any output was scored.
2. Three independent skeptic agents in fresh contexts — one counted from the definition alone by exhaustive
   backtracking — plus the kit's honesty gate and mechanical package checker.
3. A blind cross-review by OpenAI Codex, given only the instance and the definition: it first reproduced the published
   values at *n* = 7, 9, 11, 13 and 15, then counted 530,528 with two counters of its own (a rotation-lattice traversal and
   an exhaustive constraint search), comparing the full sets of matchings byte for byte.

## Why it matters

Stable matching runs real markets — medical residency, school choice — and the number of stable matchings measures how
much room a market designer has (see [001](001-stable-marriage-n15.md#why-it-matters)). Beyond the single number, the
result is a reminder that old constructions and new search results compose: a record found by computer at one size can
be lifted mechanically to another.

## What it is not

- **Not the answer to the open problem.** It raises the best known lower bound for *n* = 18; the true maximum *f(18)*
  may be higher.
- **Nothing about other sizes.** The same doubling can be applied to the other new odd-size records; those sizes are
  being checked against the published tables before anything is claimed.

## Verify it yourself

The instance, a stand-alone verifier and the review trail are in the submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-12429e3e](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-14-r-nikhil-12429e3e/known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-12429e3e).

```sh
sh verify-it-yourself/run_checks.sh        # from that folder; last line should be PASS (~5 s, needs a C compiler)
```

Instance sha256: `12429e3eb7c67d315bddabe7ac71edc070cfbaae1760c67f66b8d2fa1e61b488`.

## Credits

Gale and Shapley; Knuth; Irving and Leather; Gusfield and Irving; Thurber; Ong, Ang, Ho, Eilers, Marks and Buzi (the 9×9
record instance this result doubles); Myunglae Jo (computer-assisted proof that *f*(7) = 85); Dan Eilers (OEIS
A357269 / A357271); and the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
