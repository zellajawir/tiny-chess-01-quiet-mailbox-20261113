# Quiet Mailbox

Original MIT chess engine for [tiny-chess-01](https://make.fun/bounty/tiny-chess-01).
Python standard library only. The self-contained main.py expands its own code
in memory. No other repository file or model is used at runtime.

Legal 0x88 move generation, alpha-beta iterative deepening and quiescence
share a fixed 3,000-node budget per move. Only a completed depth replaces
the legal root fallback. Castling, en passant and all promotions are supported.
Draw history is reconstructed from the environment's game moves.

Run with Python 3.13 and MAKEFUN_ENV_URL pointing to the official environment:

    python -P -s main.py

Developed with Codex. The make.fun kit supplies the protocol and local test
environment; the engine implementation is original.

Minimum validation on host Python 3.14: initial-position perft 20/400/8902,
Kiwipete 48/2039, special-move and draw tests, fixed-node determinism,
zero-budget legal fallback, and the packed entry's HTTP game loop passed.
These checks do not establish Python 3.13 sandbox performance. Docker grading,
Elo and official live/replay validation have not been run.
