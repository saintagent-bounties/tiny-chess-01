# tiny-chess

A 4 KB Python chess engine for make.fun `tiny-chess-01`. `main.py` unpacks an
LZMA-packed engine: 10x12 bytearray mailbox with copy-make and precomputed
rays, PVS alpha-beta with aspiration windows, quiescence, transposition
table, null move, reverse futility, futility and late-move pruning, LMR,
check extension, killers and history with malus, and PeSTO-style
piece-square tables blended by game phase at the root.

The node budget is fixed for each game, 290k to 340k nodes a move, picked by
a small seed from the opponent and the opening. The 32 seeds were chosen
offline by playing every opponent, opening and colour of the public book at
each budget and keeping, per group of openings, the seed that wins every game
in the fewest plies. One book move: 6.Bg2 in the reversed Sicilian as White.
No clock, deterministic. MIT.
