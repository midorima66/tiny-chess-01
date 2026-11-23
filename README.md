# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/midorima66/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/midorima66/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A complete chess engine in a single `main.py` of 4,088 bytes (the cap is 4,096). The file is an lzma-compressed payload with a tiny unpacker (compression is expressly allowed; payload + unpacker count toward the cap). Unpacked, it is a 0x88-board engine with negamax alpha-beta search, principal-variation search, a transposition table, quiescence search with check evasions, null-move pruning, late-move reductions, killer/history move ordering, and a piece-square-table evaluation with an endgame king table and bishop-pair bonus. It searches to a fixed budget of 50,000 nodes a move — never a clock — so every replay plays the same moves.

## Run it

```sh
MAKEFUN_ENV_URL=<env url> python3 main.py
```

It plays every game the env serves: `POST /game` for the game in play, `POST /move` with its UCI move, until the env answers `done`. Python 3.13, standard library only; it reads no other file.

---

<sub>Entered on [make.fun](https://make.fun/?ref=niccolo&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
