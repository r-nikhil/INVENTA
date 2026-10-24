# Who wins misère Sprouts from 21 spots?

**Open problem.** Sprouts builds a drawing one move at a time, but in the misère version the last move loses. Does the first player win or lose from 21 initial spots in the plane? The cited conjecture predicts a loss; either independently certified outcome settles the target.

**Status.** The fetched Glop misère table lists 20 spots as a loss dated 2011-03-18 and 21 as unknown. Its introductory sentence still calls 20 the first unknown value and conflicts with the table; the explicit table rows are used here. The supplied proposal attributes Glop to Lemoine and Viennot. [Status source](<https://en.wikipedia.org/wiki/Sprouts_(game)>). Historical proposal status date: 2026-10-14. Any first-solve or best-known claim requires a further current comparison. This preparation made no new source request.

## The problem

A move draws a noncrossing curve between two spots, possibly the same spot, and adds a new spot on the curve. No spot may have more than three incident lines. A loop uses two incidences at its starting spot. The player with no legal move wins in misère play, because the opponent made the last move. Geometry matters through regions and connections, rather than the exact shape of each curve.

## Backstory

- 1967: Conway and Paterson introduced Sprouts.
- 1991: Applegate, Jacobson and Sleator computed outcomes through nine spots.
- 2009-08-30: Glop recorded a win at 17 spots.
- 2010-12-18: Glop recorded a win at 18 and a loss at 19.
- 2011-03-18: Glop recorded a loss at 20.

## Why it matters

The game shows how a small rule change can invalidate a familiar solving method. It is a concrete test of exact adversarial reasoning when independent-looking regions cannot simply be combined using normal-play rules.

## Real-world uses

A certified outcome yields a provably winning strategy for the appropriate side and a benchmark for topological move generation and proof-tree checking.

## How to think about it

The hard part is covering all legal moves without merging distinct positions. A predicted loss at the root needs every opening answered. Region decomposition may help, but ordinary nimber addition is invalid here; only justified misère reductions can be used.

## What counts as a solution

Produce a complete solution tree for the 21-spot planar position. An independent checker must regenerate every move at nodes requiring all replies, verify the selected move at other nodes, and treat no-move positions as wins. Recompute any reduced canonical trees used for decomposition. A second independent implementation must reproduce the outcome. Check that 21 remains unresolved before claiming. Certified outcomes at 22 or 23, or independent confirmation of the published 17–20 results, are separate partial targets.

## Our approach

Use canonical position descriptions and proof-number search with sound misère reductions. Rebuild legal moves independently and retain a complete checkable strategy certificate.

## Sources

Sources supplied with the proposal. Retrieval notes below come from the earlier page review. No fresh source request was made during final preparation.

- <http://sprouts.tuxfamily.org/wiki/doku.php?id=records>
- <https://en.wikipedia.org/wiki/Sprouts_(game)> — HTTP 403; not retrieved.
- <https://arxiv.org/abs/0908.4407>
- <https://arxiv.org/pdf/1008.2320>
- <https://arxiv.org/abs/2511.10339>
- <https://arxiv.org/html/2511.10339v2>
- <https://github.com/cizektom/spots>
- <http://sprouts.tuxfamily.org/wiki/doku.php?id=home>
