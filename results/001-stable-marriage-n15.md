# 001 · The most stable matchings in a 15×15 marriage market

**Result.** An explicit stable-marriage instance with 15 people on each side that has exactly **27,510** stable
matchings — more than the previous best known instance of that size (**27,059**, Ong et al., 2025). In the notation of
OEIS [A357269](https://oeis.org/A357269), this shows **f(15) ≥ 27,510**.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by
a second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #144](https://github.com/elder-plinius/V3R1T4S/pull/144).

---

## The problem

Take *n* men and *n* women (or applicants and programs, buyers and sellers). Everyone ranks everyone on the other side,
strictly, from most to least preferred. A **matching** pairs them up one-to-one. It is **stable** if there is no man and
woman who would both rather be with each other than with their assigned partners — nobody has a reason to break away.

Every such market has at least one stable matching. Many have several, and some have a great many. The question:

> **For a market of size *n*, what is the largest possible number of stable matchings?** Call it *f(n)*.

The exact answer is known only for very small markets. For larger *n*, the best we know are explicit examples (lower
bounds) and general upper bounds that are exponentially far apart.

## Backstory

- **1962 — existence.** David Gale and Lloyd Shapley, *College Admissions and the Stability of Marriage*, showed that a
  stable matching always exists and gave the "deferred acceptance" algorithm that finds one.
- **1970s — structure.** The stable matchings of an instance form a *distributive lattice*: between the matching best
  for one side and the matching best for the other lies a whole ordered family of compromises. Donald Knuth's lecture
  notes *Mariages stables* (1976) collected the theory and its open questions, including how many stable matchings an
  instance can have.
- **1986 — hardness and big examples.** Robert Irving and Paul Leather proved that counting stable matchings is #P-complete
  (as hard as counting gets) and built instances with exponentially many: for markets of size 1, 2, 4, 8, 16 their
  construction gives 1, 2, 10, 268 and 195,472 stable matchings (OEIS A005154).
- **1989 — an open problem by name.** Dan Gusfield and Robert Irving's book *The Stable Marriage Problem* lists the
  maximum number of stable matchings as an open problem.
- **2002 — every size.** Edward Thurber extended the constructions to all *n* by composing smaller instances; those
  composition bounds still define most entries of OEIS A357271.
- **2018–2021 — the ceiling.** Anna Karlin, Shayan Oveis Gharan and Robbie Weber proved the first upper bound of the form
  *cⁿ*; Cory Palmer and Dömötör Pálvölgyi tightened it to about **3.55ⁿ**. The best constructions grow like roughly
  **2.28ⁿ**, so the true growth rate is still unknown.
- **2024–2026 — computer searches.** Ryan Ong, Bethany Ang, Abigail Ho, Dan Eilers, Justin Marks and Genti Buzi used
  improved hill climbing to beat the old bounds for odd sizes 7, 9, 11, 13 and 15 (n = 15: 25,011 → 27,059), and a
  2026 computer-assisted proof (not yet peer reviewed) puts n = 7 at exactly 85. Dan Eilers maintains the OEIS entries A357269 (exact values) and
  A357271 (best lower bounds).

## Why it matters

Stable matching is not a toy. It is the engine of real markets:

- **Medical residency.** The US National Resident Matching Program assigns tens of thousands of doctors a year with a
  stable-matching algorithm (redesigned by Alvin Roth and Elliott Peranson in the late 1990s).
- **School choice.** New York City, Boston and many other systems assign students to schools this way.
- **The 2012 Nobel Prize in Economics** went to Roth and Shapley "for the theory of stable allocations and the practice
  of market design."

How *many* stable matchings a market has is a measure of how much room the designer has: with one stable matching there
is nothing to choose; with thousands, the choice between them decides who wins and who loses (one side's optimum, the
other side's, or a fairer "median" compromise), and it shapes how much participants can gain by misreporting their
preferences. The maximum *f(n)* is the extreme case of that room — a basic constant of two-sided markets, and a long-open
question in the mathematics behind them.

## What we found

An explicit 15×15 instance (15 men's rankings and 15 women's rankings) with **exactly 27,510** stable matchings, 451 more
than the best previously known instance of that size (+1.7 %).

**How.** A research lane running Claude Fable 5.1 built a fast exact counter (it walks the lattice of stable matchings),
validated it against two independent counters on every published record instance, and wrapped it in an iterated local
search: small swaps inside one person's ranking, sideways moves allowed, random kicks when stuck. Starting from the
published 27,059 instance, one search found the 27,510 instance after 1,651 evaluations — about 28 seconds. The success
rule (beat 27,059 strictly; three counters must agree) was frozen before any search ran.

**Checks it passed.**
1. Four exact counters inside the run, two of them exhaustive enumerations, all giving 27,510.
2. Three independent skeptic agents in fresh contexts: one reproduced the count with its own code (three methods and 398
   random cross-checks), one re-fetched the live OEIS table to confirm 27,059 was still the best known, one checked the
   claim against the criterion literally. Then the kit's honesty gate and its mechanical package checker.
3. A blind cross-review by OpenAI Codex, given only the instance and the definition: two counters of its own (a pruned
   pairwise search and a rotation traversal) enumerated the same 27,510 matchings — and reproduced 27,059 for the
   published instance.

## What it is not

- **Not the answer to the open problem.** It raises the best known lower bound for n = 15; the true maximum *f(15)* may
  be higher. Nothing is proved about other sizes.
- **Not a structural insight (yet).** The instance was found by search; why it works is not explained.
- **A small step.** The gain is 1.7 %. Its value is that it is new, exact and checkable by anyone in seconds — and that
  the search that found it is cheap enough to push further.

## Verify it yourself

The instance, a stand-alone verifier and the full review trail are in the submission folder:
[known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-3a7359d3](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-14-r-nikhil-3a7359d3/known-knowns/stable-marriage-max-stable-matchings/2026-10-14-r-nikhil-3a7359d3).

```sh
sh verify-it-yourself/run_checks.sh        # from that folder; last line should be PASS (~15 s, Python 3 only)
```

Instance sha256: `3a7359d3db2f878cae106c2f527763c6abf150c0788b943de38661076ab539a8`.

## Credits

Gale and Shapley; Knuth; Irving and Leather; Gusfield and Irving; Thurber; Karlin, Oveis Gharan and Weber; Palmer and
Pálvölgyi; Ong, Ang, Ho, Eilers, Marks and Buzi; Dan Eilers (OEIS A357269 / A357271); and the V3R1T4S kit by
[elder-plinius](https://github.com/elder-plinius/V3R1T4S), whose verification pipeline this result went through.
