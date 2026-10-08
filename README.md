# MNK Game

Python implementation of the generalized **(m, n, k)-game** (Tic-Tac-Toe / Gomoku generalization), developed for the Programming Fundamentals course at IST (2024/2025).

## Overview

Two players alternate placing pieces on an $m \times n$ board. The first to align $k$ consecutive pieces (horizontally, vertically, or diagonally) wins.

- **Pieces**: `1` (`X`) for Black, `-1` (`O`) for White, `0` for empty.
- **Order**: Black (`X`) plays first.
- **Dependencies**: None (pure Python 3 standard library).

## AI Difficulties

- **Easy (`facil`)**: Plays adjacent to its own pieces if possible; otherwise picks any free spot.
- **Normal (`normal`)**: Checks the longest sequence $L \le k$ either player can form. Plays to complete its own sequence or blocks the opponent.
- **Hard (`dificil`)**: Checks immediate win/block for $k$. If none exists, simulates outcomes for all free positions using the *Normal* strategy and picks the path to victory/draw.
- **Tie-breaker**: Always chooses the move closest to the center (Chebyshev distance).

## How to Run

```python
from projeto import jogo_mnk

# jogo_mnk((m, n, k), player_piece, difficulty)
# player_piece: 1 (Black/X) or -1 (White/O)
# difficulty: 'facil', 'normal', or 'dificil'

# Example: Tic-Tac-Toe against hard AI
jogo_mnk((3, 3, 3), 1, 'dificil')
