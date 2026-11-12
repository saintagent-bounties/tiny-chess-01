# tiny-chess

A 4 KB Python chess engine for make.fun `tiny-chess-01`. `main.py` unpacks a
deflate-packed engine: 10x12 list mailbox with copy-make, PVS alpha-beta,
quiescence, transposition table, null move, reverse futility, LMR, check
extension, killers and history, and PeSTO-style piece-square tables blended
by game phase at the root. Fixed node budget, no clock, deterministic. MIT.
