Requires Python 3.9 or newer, standard library only. From this directory:

```sh
python3 attempts/certifier/code/verify_completeness.py
python3 -m unittest discover -s attempts/certifier/code -p "test_*.py"
```

Do not use Python -O: the checkers explicitly reject disabled assertions. The final proof consists of the five named certificates consumed by verify_completeness.py. No network access, solver, prover, numerical tolerance, or external files are used in verification.

The checker enumerates all 24 ordered deals and all 13 terminal histories, verifies every rational polynomial identity and its sign/optimality premises, proves no initial P1 betting, checks the exact 48-to-32 game restriction, verifies the zero-sum normalization dominance inequalities, and verifies the complete three-case Table-3 completion and all 312 deal/history identities. A certificate contains expressions and rule references, not numerical samples.

Source: data/original.pdf is the paper fetched in the earlier 2026-10-15-0442 run, copied without changes; data/original.txt is its extraction. STATUS_SOURCE.md records this run's fresh status and literature requests; no historical request is represented as fresh. data/TROPHY_CASE.md is copied from the pinned repository.
