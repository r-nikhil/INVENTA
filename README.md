# INVENTA

**Things found.** Open problems attacked by autonomous Claude research agents, every result checked by skeptics and
reproducible by anyone in seconds. Each discovery gets one plain-language write-up: what the problem is, where it came
from, why it matters, what we found, and how you can verify it yourself.

> *Inventa* (Latin): "things discovered". A companion to [V3R1T4S](https://github.com/elder-plinius/V3R1T4S), the open
> research kit our agents run on, where every result is also submitted for independent review.

## Results

| # | Date | Problem | Result | Status | Verify |
|---|---|---|---|---|---|
| 001 | 2026-10-14 | [Most stable matchings in a 15×15 marriage market](results/001-stable-marriage-n15.md) | 27,510 stable matchings (previous best known: 27,059) | Submitted to V3R1T4S ([draft PR #144](https://github.com/elder-plinius/V3R1T4S/pull/144)) | ~15 s, Python only |
| 002 | 2026-10-15 | [Most stable matchings in an 18×18 marriage market](results/002-stable-marriage-n18.md) | 530,528 stable matchings (previous best known: 456,300) | Submitted to V3R1T4S ([draft PR #147](https://github.com/elder-plinius/V3R1T4S/pull/147)) | ~5 s, C compiler |

## How a result gets here

1. **Hunt.** Several agent lanes (Claude Opus and Fable models) work through open problems that have a public record
   table or a precise definition, so that any answer is checkable by a stranger's computer.
2. **Gauntlet.** A claim must survive the V3R1T4S kit: a frozen success rule, three independent skeptic agents in fresh
   contexts (reproduce, novelty, criterion), and an honesty gate.
3. **Cross-model review.** A different model family (OpenAI Codex) re-derives the result blind, from the definition alone.
4. **Submit.** Only then is it packaged with a self-contained verifier and submitted upstream; it is written up here.

Most runs find nothing; that is expected. Only results that passed every step appear in the table.

## Log

Running updates: [LOG.md](LOG.md).

## Licence

Text: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Objects and verifiers live with each V3R1T4S submission
under that repository's licences.
