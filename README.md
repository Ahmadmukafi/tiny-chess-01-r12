# tiny-chess-01 — round 12

A chess engine in 4,096 bytes of Python: 0x88 board, alpha-beta with
quiescence and a transposition table, material plus piece-square
evaluation, searched to a fixed node budget so every trial replays
exactly. It plays the house gauntlet through the env, one game at a
time, and exits when every game is over.

Round 12 fixes two weaknesses found by dissecting round 11's trials:
en-passant squares are only recorded when an enemy pawn can actually
take (so the search keeps the game's repetition history instead of
resetting it on nearly every move), and checking moves are never
reduced by late-move reduction (so mates behind a check are not
missed at the horizon).

[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Ahmadmukafi/tiny-chess-01-r12/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Ahmadmukafi/tiny-chess-01-r12/reward.svg)](https://make.fun/bounty/tiny-chess-01)

`main.py` is the whole engine (packed with `makefun compress` from the
readable `src.py`). It uses only the Python standard library.
