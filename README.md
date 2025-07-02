# 🧠 GAME-AI: A Python Chess Bot


This repository contains a fully functional chess game built in Python, where you can play against an intelligent AI opponent. The AI is powered by the NegaMax algorithm, a variant of Minimax, enhanced with Alpha-Beta Pruning for efficient decision-making. The game features a complete graphical user interface using Pygame.

## ✨ Features

-   **Play Against AI:** Challenge a chess bot that calculates moves multiple steps ahead.
-   **Human vs. Human:** The game also supports a two-player mode on the same screen.
-   **Complete Chess Logic:** Full implementation of all standard chess rules, including pawn promotion, castling, and en passant.
-   **Interactive GUI:** A clean, responsive interface built with Pygame.
-   **Move Highlighting:** Click a piece to see all its valid moves highlighted on the board.
-   **Move Log:** A running log of all moves made during the game, displayed in standard algebraic notation.
-   **Game Controls:**
    -   `Z` key to undo the last move.
    -   `R` key to reset the board and start a new game.

## 🛠️ Technology Stack

-   **Language:** Python
-   **Library:** Pygame (for the GUI, event handling, and sound)
-   **AI Algorithm:** NegaMax with Alpha-Beta Pruning

## 🚀 Getting Started

Follow these steps to get the game running on your local machine.

### Prerequisites

-   Python 3.x
-   pip (Python package installer)

### Installation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/khem75/game-ai.git
    ```

2.  **Navigate to the project directory:**
    ```sh
    cd game-ai
    ```

3.  **Install the required packages:**
    ```sh
    pip install pygame
    ```

4.  **Run the game:**
    ```sh
    python chess-ai/chess/main.py
    ```

## 🤖 AI Configuration

You can easily configure the AI's behavior and difficulty by editing the source files.

### Setting Player Sides

To decide whether a human or the AI controls White or Black, modify the following boolean flags in `chess-ai/chess/main.py`:

```python
# Set to True to make the AI play White
SET_WHITE_AS_BOT = False 

# Set to True to make the AI play Black
SET_BLACK_AS_BOT = True 
```

### Adjusting AI Difficulty

The AI's strength is determined by its search depth. You can change this by modifying the `DEPTH` variable in `chess-ai/chess/chessAi.py`.

-   A higher depth means the AI thinks more moves ahead, making it stronger but also slower.
-   A depth of `2` or `3` is recommended for a good balance of performance and difficulty.

```python
# The number of moves the AI looks ahead.
DEPTH = 2
```

### Flipping the Board

If you wish to play as Black from your perspective at the bottom of the screen, you can flip the board orientation. In `chess-ai/chess/engine.py`, change the following line in the `GameState` class constructor:
```python
# Set to True to flip the board
self.playerWantsToPlayAsBlack = True
```

## 📂 Project Structure

-   `chess-ai/chess/main.py`: The main entry point for the application. It initializes Pygame, handles the game loop, processes user input, and manages the overall game flow.
-   `chess-ai/chess/engine.py`: The core of the chess game's logic.
    -   `GameState`: Manages the board state, move history, and enforces all chess rules.
    -   `Move`: A class representing a single move, containing start/end coordinates and any special flags (e.g., castling).
-   `chess-ai/chess/chessAi.py`: Contains the AI's "brain".
    -   Implements the NegaMax algorithm with Alpha-Beta pruning to search for the best move.
    -   Includes a sophisticated `scoreBoard` function that evaluates board positions based on material and piece-square tables.
-   `images1/`: Contains the `.png` images for all the chess pieces.
-   `sounds/`: Contains the sound effects for moves, captures, and promotions.
