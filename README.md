# Tic Tac Toe Game Design

This repository contains a complete **Tic Tac Toe** game design captured entirely within a single YAML file. The file includes pseudocode, Python implementation, flowchart, and an example of serialized game state. It's designed to provide a cohesive resource for learning and building Tic Tac Toe from scratch.

---

## Overview

### What's Inside?
1. **Pseudocode**: Step-by-step explanation of the game's logic and workflow.
2. **Python Implementation**: Full code for the Tic Tac Toe game, including win/draw checks, move validation, and restarting functionality.
3. **Flowchart**: Visual game flow representation using Mermaid syntax for clarity.
4. **JSON Example State**: Demonstrates how game states are serialized after a few moves.

### Why YAML?
- Combines planning, implementation, and visualization into one format.
- Easy to modify, share, and adapt for different projects.
- Suitable for educational purposes, helping learners understand game development end-to-end.

---

## Features

### 🔢 Game Logic
- **Board Size**: Standard 3x3 grid.
- **Win Condition**: Align 3 consecutive marks in a row, column, or diagonal.
- **Draw Detection**: Declares a draw if no spaces remain.

### 🔁 Key Functionalities
- **Restart Game**: Reset the board and start fresh.
- **Player Switch**: Alternate turns between 'X' and 'O'.
- **Win and Draw Checks**: Dynamically detect outcomes and end the game appropriately.

### 📊 Game Flow
The Mermaid flowchart illustrates the game's logic in detail:
```mermaid
graph TD
  Start[Start Game] --> Init[Initialize Board and Variables]
  Init --> GameLoop[Game Loop (Until Game Over)]

  GameLoop --> Display[Display Board]
  Display --> PlayerAction{Player Action}

  PlayerAction -- Move --> ValidateMove[Validate Move]
  ValidateMove -- Invalid --> GameLoop
  ValidateMove -- Valid --> Update[Update Board and Save Move]
  Update --> CheckWin[Check Win?]

  CheckWin -- Yes --> Win[Announce Winner]
  CheckWin -- No --> CheckDraw[Check Draw?]
  CheckDraw -- Yes --> Draw[Announce Draw]
  CheckDraw -- No --> Switch[Switch Player] --> GameLoop

  PlayerAction -- Restart --> Restart[Restart Game] --> Init
  PlayerAction -- Quit --> End[Exit Game]

  Win --> PlayAgain[Play Again?]
  Draw --> PlayAgain
  PlayAgain -- Yes --> Init
  PlayAgain -- No --> End
