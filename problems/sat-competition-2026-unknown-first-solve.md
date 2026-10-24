# A first certified answer for an unknown SAT instance

**Open problem.** Can we settle a Boolean formula that remains unanswered in the SAT Competition 2026 Main-track benchmark database? The target is one instance whose database result is still “unknown” at verification time: either exhibit a satisfying assignment or provide a formally checked proof that no assignment exists.

**Status.** The fetched Global Benchmark Database has 400 main_2026 rows, of which exactly 40 have result “unknown”. The scores comparison excludes hash 3c51a565526faa922fb298a2658440e9 because it received a competition answer, leaving 39 eligible candidates. A candidate must pass both checks. An unknown entry does not prove that no answer exists elsewhere. [Status source](<https://benchmark-database.de/?track=main_2026>). Historical JSON source-check date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison.

## The problem

A Boolean variable is true or false. A clause joins literals with OR; a CNF formula joins clauses with AND. For example, (x OR y) AND (NOT x) is satisfied by x = false and y = true. A SAT certificate is an assignment satisfying every original clause. An UNSAT certificate is a checkable derivation showing that all assignments fail. The benchmark’s normalized hash identifies the exact instance.

## Backstory

- 2004–2022: The input traces some still-unknown instances to earlier competition tracks.
- 2026: The Main track used 400 formulas and required models for SAT answers and proofs for UNSAT answers.
- 2026-10-14: The supplied database snapshot listed 40 unknown instances, spanning both older and newly submitted families.

## Why it matters

SAT is a common language for exact constraint problems. A certified answer can resolve a concrete scheduling, circuit, mathematical or security benchmark while testing whether a search method handles structure that existing runs missed.

## Real-world uses

The listed families include school timetabling, station repacking, circuit minimization, polynomial multiplication and syndrome decoding. A model is a feasible solution to the encoded problem; an UNSAT proof establishes impossibility for that exact encoding.

## How to think about it

Longer runtime alone offers no guarantee. Useful angles include identifying XOR structure, selecting informative branching variables and splitting the search into subproblems. Any preprocessing or alternative encoding must preserve a route back to the original formula. Combining proofs from subproblems also requires proving that the subproblems cover every case.

## What counts as a solution

Select a still-unknown main_2026 instance by its normalised database hash. Check that no configuration in the cited scores answered it, exclude hash 3c51a565526faa922fb298a2658440e9, and establish that it has no later published answer. For SAT, independently check a complete assignment against the original, unpreprocessed CNF. For UNSAT, provide a proof accepted by a formally verified competition-compatible checker, such as cake_lpr, gratchk or the VeriPB/CakePB chain. Save the checker version, acceptance output and proof hash. A solver’s verdict alone is insufficient. Acceptance only by an unverified checker is a separately labelled partial result under the proposal’s conditions.

## Our approach

Triage the supplied benchmark families, then pursue structure-aware search on selected instances. Preserve original formulas and build independent model or proof validation into the workflow.

## Sources

The sources and retrieval limits below come from the supplied batch A page. They were not fetched again during preparation.

- <https://satcompetition.github.io/2026/>
- <https://satcompetition.github.io/2026/tracks.html>
- <https://satcompetition.github.io/2026/output.html>
- <https://satcompetition.github.io/2026/rules.html>
- <https://satcompetition.github.io/2026/downloads.html>
- <https://satcompetition.github.io/2026/downloads/scores.csv>
- <https://satcompetition.github.io/2026/downloads/track_main_2026.uri>
- <https://benchmark-database.de/?track=main_2026>

## Preparation status

The proposal and page were reconciled locally. No result is claimed. The source check is historical; re-check the named status source before attacking or claiming. Values in unmerged pull requests are not comparison bars.
