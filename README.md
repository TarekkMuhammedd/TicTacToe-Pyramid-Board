# Pyramid Game

A simple console-based tic-tac-toe variant played on a pyramid-shaped board. You can play against a friend or against a computer opponent.

## Overview

The game board is a 3x5 grid where some cells are blocked, forming a pyramid shape. Players take turns placing their symbol (`X` or `O`) in an empty cell. The first player to align three of their symbols horizontally, vertically, or diagonally wins. If every playable cell fills up without a winner, the game is a draw.

## Features

- **Two-player mode:** two humans take turns on the same keyboard.
- **Versus computer mode:** you play against a computer that picks a random valid move. The computer always uses the symbol you did not choose.
- **Input validation:** rejects moves outside the board, moves into blocked cells, and moves into cells that are already taken.
- **Win and draw detection:** checks every row, column, and diagonal after each move.

## Project Structure

The code is organized around a few classes and functions:

| Name | Type | Purpose |
| --- | --- | --- |
| `Player` | Class | Stores a player's name and symbol. `SetSymp` ensures the symbol is valid (`X` or `O`). |
| `RandomPlayer` | Class | Computer player that inherits from `Player`. `get_move` selects a random valid cell. |
| `InitBoard` | Function | Builds the pyramid-shaped board, marking blocked cells with `-` and empty cells with `[ ]`. |
| `ValidCell` | Function | Checks that a chosen cell is within bounds and empty. |
| `IsWinner` | Function | Checks rows, columns, and diagonals for a winning line. |
| `IsDraw` | Function | Returns true when all playable cells are filled. |
| `PrintBoard` | Function | Displays the current board. |
| `PutInCell` | Function | Prompts the human player for a row and column and places their symbol. |
| `GameMaster` | Function | Runs the game loop, alternating turns until there is a win or a draw. |
| `PrintWinner` | Function | Announces the result at the end of the game. |
| `With2Players` | Function | Runs the two-human game mode. |
| `WithComp` | Function | Runs the human-versus-computer game mode. |
| `ThePyramidGame` | Function | Entry point. Asks the player to choose a game mode and starts the game. |

## Requirements

- Python 3.x
- No external libraries are required. The game uses only the standard library.

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```

2. Run the game. Replace `pyramid_game.py` with the actual file name:

   ```bash
   python pyramid_game.py
   ```

3. Choose a game mode when prompted:
   - Play with a friend, or
   - Play against the computer.

4. Enter your name and symbol when prompted. In computer mode, you choose your symbol and the computer takes the other one.

5. On your turn, enter the row and column of the cell you want to fill.

## How It Works

1. `ThePyramidGame` starts the program and asks for a game mode.
2. `InitBoard` creates the board with blocked and empty cells.
3. Players enter their names and symbols.
4. `GameMaster` alternates turns. Human moves go through `PutInCell`. Computer moves come from `RandomPlayer.get_move`.
5. After every move, the game checks for a winner or a draw.
6. When the game ends, the final board is shown and `PrintWinner` announces the result.

## Author

Tarek Muhammed Abdel-Hamid

Date : 9/08/2024


