# tiny-chess

A 4 KB Python chess engine for make.fun `tiny-chess-01`. `main.py` unpacks an
LZMA-packed engine: 10x12 bytearray mailbox with copy-make and precomputed
rays, PVS alpha-beta with aspiration windows, quiescence, transposition
table, null move, reverse futility, futility and late-move pruning, LMR,
check extension, killers and history with malus, and PeSTO-style
piece-square tables blended by game phase at the root. Fixed node budget
per opponent, no clock, deterministic. MIT.
