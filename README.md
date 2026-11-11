# tiny-chess

A 4 KB Python chess engine for make.fun `tiny-chess-01`. `main.py` is an
lzma-packed alpha-beta engine: 0x88-style 120-square board (sunfish-style
rotation, original code), PVS, quiescence, transposition table, null move,
LMR, killers and history, tapered middlegame/endgame piece-square eval.
Fixed node budget, no clock, deterministic. MIT licensed.
