# tiny-chess-01

A 4 KB chess engine in Python 3.13, standard library only. `main.py` is
4,081 bytes: an lzma-compressed payload (4,018 bytes of base85) plus the
unpacker that execs it.

[![tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/verlianmr/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/verlianmr/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01)

## How it plays

A 0x88 board with Zobrist hashing. Iterative deepening alpha-beta with
principal variation search, a transposition table, null-move pruning,
check extension and a capture-only quiescence search, ordering moves by
capture value. The evaluation is material plus piece-square tables, with
castling and repetition handled in the hash. The search is fixed by
depth and a node cap, never a clock, so every trial replays exactly.
