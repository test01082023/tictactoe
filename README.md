 # Tic Tac Toe Game Design

This repository provides a comprehensive design for **Tic Tac Toe**, encapsulated entirely within a single YAML file. The file integrates all essential components, from pseudocode and Python implementation to flowchart visualization and example game states, offering both clarity and functionality.

---

## What's Inside?

### 1. **Pseudocode**
Step-by-step instructions outlining the game logic:
- Initialization of the board and game variables.
- A structured loop for gameplay, including win/draw checks and actions like restart or quit.

### 2. **Python Implementation**
Complete game functionality implemented in Python:
- Player interaction with move validation.
- Automated checks for win and draw conditions.
- Features such as restarting the game and quitting during gameplay.

### 3. **Flowchart**
Visual representation of the game's workflow using **Mermaid syntax**:
- Illustrates key steps such as validating moves, checking for win/draw, switching players, and ending the game.

### 4. **Example JSON Game State**
Provides a snapshot of the game's state after several moves to demonstrate serialization.

---

## Features

### 🔢 Game Logic
- **Board Size**: Standard 3x3 grid.
- **Win Condition**: Place 3 consecutive marks in a row, column, or diagonal to win.
- **Draw Detection**: Declares a draw if no spaces remain and no player has won.

### 🔁 Key Functionalities
- **Restart Game**: Reset all variables to start fresh.
- **Switch Player**: Automatically alternates turns between 'X' and 'O'.
- **Game Ending**: Checks for win/draw conditions to conclude the match.

### 📊 Flowchart
The flowchart below visually represents the game's logic:
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
