# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/zhuceyici2046-png/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/zhuceyici2046-png/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A tiny chess engine in 4 KB of Python: alpha-beta search with quiescence, piece-square evaluation, and a deterministic fixed node budget. It plays the house gauntlet through the make.fun env, one game after another.

## Engine

- **Board:** 0x88 representation with full legal move generation — pawns (including en passant and promotion), castling, check, checkmate and stalemate.
- **Search:** negamax alpha-beta with quiescence search, iterative deepening to a fixed 100,000-node budget. The budget is fixed and there is no clock or randomness, so the engine is fully deterministic.
- **Ordering and memory:** transposition table, killer moves and MVV-LVA move ordering; the best move from the previous iteration is tried first at the root.
- **Evaluation:** material plus piece-square tables, a bishop-pair bonus and a phase-dependent king table — the king stays home in the middlegame and centralises in the endgame.
- **Correctness:** perft is exact on 5 standard positions (start position, Kiwipete, en passant, promotion/castling and a fifth test position), and make/unmake is consistent over random playouts.
- **Strength:** about 1,145 Elo in a local 12-game gauntlet against depth- and node-limited opponents.

## Run it

Start the gauntlet environment, then point the engine at it with `MAKEFUN_ENV_URL`:

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=dn6vattq&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
