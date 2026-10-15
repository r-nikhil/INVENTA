# C01 · Candidate: every Nash equilibrium of 3-player Kuhn poker is in the Szafron–Gibson–Sturtevant family

> **Status: candidate, not confirmed.** This has NOT been through the full V3R1T4S gauntlet and is not submitted
> anywhere. Two independent skeptics passed it (one reproduced and re-checked the proof, one judged it against the
> problem's success rule), but the novelty review is incomplete: one source, a textbook chapter, could not be read
> (details below). Every step of this pipeline ran on OpenAI Codex models, so no second model family has reviewed it.
> We publish it so that anyone can check it.

**Claim.** Every behavioural Nash equilibrium of the three-player Kuhn poker game defined in Section 2 of Szafron,
Gibson and Sturtevant (AAMAS 2013) agrees, at every information set it reaches with positive probability, with some
member of their Tables 2–3 family.

## The problem

Kuhn poker is the classic toy poker game: a tiny deck, one betting round, bet or check, call or fold. The two-player
game was solved by Kuhn in 1950. The three-player version (four cards, introduced by Abou Risk and Szafron in 2010) is
much harder. Szafron, Gibson and Sturtevant (2013) found a whole family of Nash equilibria analytically, parameterised by
four to six numbers. In every member, player 1 always checks first and player 2's expected result is fixed at −1/48
per hand, while player 2 can shift money between the other two players without leaving equilibrium. Whether that family
contains **every** Nash equilibrium has been open since 2013. As of 2026 Wikipedia's Kuhn poker article still says "It is
not known if this equilibrium family covers all Nash equilibria for the game" (page last edited 10 July 2026, checked by
hand on 2026-10-15).

Why it matters: it would make three-player Kuhn poker the largest multi-player poker game whose equilibria are completely
understood, a reference point for testing multi-player poker solvers, which have no general equilibrium guarantees.

## What the proof does

It is a computer-checked proof in exact rational arithmetic, with five certificates:

1. **No initial bet:** in every Nash equilibrium player 1 never opens with a bet.
2. **Normalisation:** preconditions and dominance identities that reduce the 48 behavioural probabilities of the game
   to a 32-coordinate normal form.
3. **Restricted family:** the equilibrium conditions on the 18 coordinates that matter, solved in closed form.
4. **Terminal family:** all 24 ordered deals and all 13 terminal histories (312 deal-history cells) checked against the
   family's terminal-history distribution.

The checker reads only the certificates and verifies every rational polynomial identity and every sign condition. It
uses no solver, no network and no floating point.

## Check it yourself

From [`c01-files/`](c01-files/), with Python 3.9 or newer (standard library only):

```sh
python3 attempts/certifier/code/verify_completeness.py
python3 -m unittest discover -s attempts/certifier/code -p "test_*.py"
```

The first command should end with `FULL_GAME_COMPLETENESS: PASS` (under a second on a laptop). Do not use `python3 -O`:
the checkers reject disabled assertions. The proof notes are `NORMALIZATION_PROOF.md` and `TERMINAL_LAW.md`;
`CLAIM.md` and `REPRODUCE.md` are the claim as the skeptics saw it. The copies of the source paper and literature that the
run used are not included (copyright); `REPRODUCE.md` mentions them by name.

## Why it is not confirmed

- **Reproduce: passed.** A fresh skeptic re-ran and re-derived every certificate check, including zero-reach and
  boundary cases and all 2,241 proof events.
- **Criterion: passed.** A fresh skeptic judged the claim to meet the problem's success rule, with the scope stated above.
- **Novelty: failed, on one unread source.** The automated status fetch of the Wikipedia page was blocked (HTTP 403), so
  a human checked it by hand. The literature search (Crossref, OpenAIRE, arXiv, the last 24 months, open pull
  requests) found no earlier proof. One source could not be read at all: Erich Prisner, *Game Theory Through Examples*
  (MAA, 2014), chapter "Example: VNM POKER and KUHN POKER", pp. 185–192
  ([doi:10.5948/9781614441151.026](https://doi.org/10.5948/9781614441151.026)). It is very likely about two-player
  models, but under the kit's rules an unread source blocks confirmation. **If you can read that chapter, please tell us
  what it covers.**

## Credits

Harold W. Kuhn (the game); Nick Abou Risk and Duane Szafron (the three-player variant); Duane Szafron, Richard Gibson and
Nathan Sturtevant (the equilibrium family and the open question). The proof and checkers were written by a V3R1T4S
research lane running OpenAI Codex (gpt-6-astra).
