# 007 · A slightly higher floor for combining two forecasters

**Result.** An explicit pair of information structures (each chosen with probability 1/2) that forces *every* way of
combining two experts' forecasts to have worst-case regret at least

**1652448303171916717080006468042849 / 70681471350112364987160770000000000 ≈ 0.0233788045**,

just above the best published lower bound **31/1326 ≈ 0.0233785822** for this setting (Chen, Peng and Tang,
[arXiv:2604.24517](https://arxiv.org/abs/2604.24517) v2, Table 1 and Theorem 3.4). The gain is tiny, about
**2.2 × 10⁻⁷**, and it exists only in exact arithmetic: both numbers print as 0.023379 at six decimals.

**Status.** Confirmed by the V3R1T4S gauntlet (three independent skeptic agents + honesty gate), cross-checked blind by
a second model family, and submitted for maintainer review:
[elder-plinius/V3R1T4S draft PR #160](https://github.com/elder-plinius/V3R1T4S/pull/160). It does **not** reach the
+10⁻⁵ margin that our own bank entry for this problem asks for ([merged PR #154](https://github.com/elder-plinius/V3R1T4S/pull/154)),
so in the bank's sense the problem is still open.

---

## The problem

Two experts each see a private signal and report a probability; you must merge the two reports without knowing how
their information was generated, only that their signals are independent given the true state. Regret is your
expected squared error minus that of an omniscient aggregator who saw both signals. See the
[problem page](../problems/robust-forecast-aggregation-bounds.md) for the backstory and why it matters for prediction
markets and forecast pooling.

## What we found

Lower bounds here come from an adversary: pick a mixture of information structures, compute the best possible
aggregator *for that mixture*, and its regret is a floor for everyone. The paper's own adversary mixes two mirror-image
structures with binary signals (reports 1/6 and 5/6). We kept that shape and searched the numbers: reports
6693/40000 and 33307/40000, states {0, 33307/40000} and {6693/40000, 1}, with matching priors. The regret of the best
aggregator on this mixture, computed as an exact fraction, is the value above.

**Checks it passed.** Three exact computations in two separately written programs inside the run; three skeptic agents
in fresh contexts plus the honesty gate and the package checker; and a blind cross-review by OpenAI Codex, which first
rebuilt the paper's 31/1326 from its stated construction and then recomputed this bound exactly by two independent
methods (exact conditional variance; exact enumeration of the squared loss), getting the same fraction.

## What it is not

- Not a new kind of construction, and not optimal: only two-structure, two-report mixtures were searched.
- Nothing about the upper bound (0.025512) or the binary-state cell; the gap stays almost as wide as before.
- Not a solution under the bank entry's margin (+10⁻⁵): see the status note above.

## Verify it yourself

Submission folder:
[known-knowns/robust-forecast-aggregation-bounds/2026-10-15-r-nikhil-c8c3d23d](https://github.com/r-nikhil/V3R1T4S/tree/claim/2026-10-15-r-nikhil-c8c3d23d/known-knowns/robust-forecast-aggregation-bounds/2026-10-15-r-nikhil-c8c3d23d)
— run `sh verify-it-yourself/run_checks.sh` there (about 2 seconds, Python 3 standard library); the last line should be `PASS`.

Object sha256: `c8c3d23d5e791ec2c2d51a0ce5555fa7af7e9712d0c0ad0acd31f7bdbdc0b971`.

## Credits

Chen, Peng and Tang (the model, the bounds and the adversary shape); Arieli, Babichenko and Smorodinsky (robust forecast
aggregation); the V3R1T4S kit by [elder-plinius](https://github.com/elder-plinius/V3R1T4S).
