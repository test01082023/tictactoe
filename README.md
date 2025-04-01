# Tic Tac Toe Game Design

This repository contains a complete **Tic Tac Toe** game design embedded in a single YAML file. The file provides everything needed to understand, implement, and extend the game, from pseudocode to Python implementation, flowchart, and example game state.

---

## Overview

### What's Inside?
1. **Pseudocode**: Step-by-step logic for gameplay, including win/draw checks and restart functionality.
2. **Python Implementation**: Full code for a Tic Tac Toe game, including player actions, move validation, and game logic.
3. **Flowchart**: Visual representation of the game flow for better understanding.
4. **JSON Example State**: A sample serialized game state to illustrate how data is stored.

### Why YAML?
- Consolidates all game-related components into one cohesive file.
- Easy to read, share, and adapt for educational or developmental purposes.
- Perfect for learners and developers to explore the game design process.

---

## Features

### 🔢 Game Logic
- **Board Size**: Standard 3x3 grid.
- **Win Condition**: Align 3 consecutive marks (horizontally, vertically, or diagonally).
- **Draw Detection**: Declares a draw if no spaces remain.

### 🔁 Key Functionalities
- **Restart Game**: Reset the board and start over.
- **Player Switch**: Alternate turns between 'X' and 'O'.
- **Win Check**: Dynamic detection of a win in rows, columns, or diagonals.

### 📊 Game Flow
The following flowchart (in Mermaid syntax) illustrates the game's logic:
```mermaid
graph TD
  Start[Start Game] --> Init[Initialize Game]
  Init --> Loop[Main Game Loop]
  Loop --> Board[Display Board]
  Board --> Action{Choose Action}
  Action -- Move --> Validate[Validate Move]
  Validate -- Invalid --> Loop
  Validate -- Valid --> ApplyMove[Apply Move]
  ApplyMove --> CheckWin[Check Win]
  CheckWin -- Yes --> EndWin[Declare Winner]
  CheckWin -- No --> CheckDraw[Check Draw]
  CheckDraw -- Yes --> EndDraw[Declare Draw]
  CheckDraw -- No --> Switch[Switch Player] --> Loop
  Action -- Restart --> RestartGame[Restart Game] --> Loop
  EndWin --> End[Game Over]
  EndDraw --> End
