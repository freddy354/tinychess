# Tiny Chess — a 4 KB Python chess engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/freddy354/tinychess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/freddy354/tinychess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An entry for the make.fun bounty [`tiny-chess-01`](https://make.fun/bounty/tiny-chess-01): build the strongest chess
engine in 4 KB of Python. `main.py` (3,967 bytes) is the whole engine.

## How it fits

`main.py` is the full engine compressed with lzma via the kit's `makefun compress`
(makefun-compress/v1), plus a small unpacker — the same form the house baseline
(sunfish) uses, and explicitly allowed by the rules. The uncompressed engine
(`main7.py`, 10,496 bytes) is a 0x88-board negamax search with alpha-beta,
a fixed 60,000-node budget (deterministic, no clock), transposition table,
killers, MVV-LVA ordering, null-move pruning, LMR, quiescence search, and
a tapered midgame/endgame evaluation with piece-square tables and pawn
structure. Perft-validated (startpos d3 = 8,902).

## Practice result

Practice trial 0 on the packed entry: **Elo 1,279** (3W 0D 3L, all games by
checkmate), above the 1,154 floor to enter the final. Direct 12-game match
vs the sunfish baseline: 5.5/12, roughly even.

## Files

- `main.py` — the engine (3,967 bytes, cap 4,096)
- `LICENSE` — MIT
