# Can two Beggar-My-Neighbour histories merge before ending?

**Open problem.** Can two reachable histories merge and then terminate?

**Status.** Primary sources retrieved once on 2026-10-24 UTC. The cited source leaves the question open; this audit did not repeat a broader search for later literature. [Status source](<https://arxiv.org/pdf/2602.23406>).

## The problem

Find two distinct, balanced starting deals whose play reaches different states that have the same next trick-boundary state. From that shared state, the match must eventually end.

## Backstory

Nicolas Andorno, Giulio Cernoia, Simone Duiz and Alessandro Michelangeli formalize the game’s dynamics. Section 13 of their July 2026 revision asks for this missing trajectory type. Infinite games and reachable collisions leading to infinite play are already known.

## Why it matters

Deterministic forward play need not preserve history. A terminating collision would show exactly how information can disappear even in a match with a finite outcome.

## Real-world uses

The witness can test game simulators, reverse-search methods and state-space analysis. The immediate application is a reproducible example in a deterministic card game.

## How to think about it

Use the paper’s (N,R) rules: four copies of every challenge rank, ordinary cards, equal initial decks, and player A leading. A state records both ordered decks and the next leader. Card collection order is part of the rule, so matching deck sizes or winner identities is insufficient.

## What counts as a solution

Supply both balanced deals, their traces to distinct predecessors x and y, a shared successor F(x)=F(y), and the complete terminating suffix. An independent simulator must replay every card and preserve all multiplicities.

## Our approach and status

Hash trick-boundary states from many balanced starts and retain distinct predecessors of a shared state. Replay candidates using a separate implementation. This proposal supplies a search target and no new game trace.

## Sources

- <https://arxiv.org/pdf/2602.23406>
- <https://www.richardpmann.com/beggar-my-neighbour-records.html>
