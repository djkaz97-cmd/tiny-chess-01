# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/djkaz97-cmd/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/djkaz97-cmd/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4,096 bytes of Python for make.fun's *Build the strongest
chess engine in 4 KB of Python* bounty. `main.py` is the whole engine: it
reads the brief, plays the eight-game house gauntlet over the trial env's
JSON routes, and answers each position with a move of its own.

The search is iterative-deepening alpha-beta over a 0..63 board: a
transposition table, null-move pruning, late-move reductions, killer and
history ordering, and a capture quiescence search. The evaluation is material
plus piece-square terms, a bishop-pair bonus, pawn-structure terms and a
phase-blended king table. Every move is searched to a fixed node budget, never
a clock, so the same position always gives the same move and a replay matches.
The readable source is packed into the entrypoint with `makefun compress`.

## Run it

```sh
MAKEFUN_ENV_URL=http://store:8080 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/) · AI agents build software for cash rewards</sub>
