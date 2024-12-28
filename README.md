# Tetris2048 Game

## Overview

Tetris2048 is a Java-based game that combines the mechanics of the classic Tetris game with the number-merging logic of the popular 2048 puzzle. The game features a graphical grid where tetrominoes fall, merge based on their numbers, and score points. Players can control the tetrominoes' movement and rotation while aiming to maximize their score before the game ends.

![image](https://user-images.githubusercontent.com/110589752/188482655-82b7ae1e-7db0-4ca6-acc4-d560c9d7e20a.png)

- You can find the demo video of the project [here.](https://drive.google.com/file/d/1XaQPz4KUzTgGX5y3uey2N5CHaRBhTOiN/view?usp=sharing)

## Features

### Core Gameplay
- **Tetrominoes**:
  - Seven different shapes (`I`, `S`, `Z`, `O`, `T`, `L`, and `J`).
  - Each tile of a tetromino is assigned a number (`2` or `4`) and a corresponding color.
  - Tetrominoes can move left, right, and down or rotate clockwise.

- **2048 Merging Mechanic**:
  - Tiles with the same number merge to form a new tile with the sum of their values.
  - Merged tiles update their color based on the resulting value.

- **Scoring**:
  - Points are scored based on the numbers on merged tiles.
  - The current score is displayed on the screen.

### Grid and Controls
- **Game Grid**:
  - A 12x20 grid serves as the game area.
  - Lines filled with tiles are cleared, and tiles above fall down.

- **Player Controls**:
  - Arrow keys to move tetrominoes:
    - `Left Arrow`: Move left.
    - `Right Arrow`: Move right.
    - `Up Arrow`: Rotate clockwise.
  - Mouse click to pause and resume the game.

### Visuals
- Graphical representation of the grid, tiles, and tetrominoes using the `StdDraw` library.
- Colors and numbers on tiles update dynamically during the game.
- "Game Over" message displayed when the game ends.

## Implementation Details

### Classes

#### `Tetris2048`
- Main game loop and entry point.
- Manages tetromino creation, player input, and game progression.

#### `Grid`
- Represents the game grid.
- Tracks tiles, handles merging and line-clearing mechanics, and updates the game state.

#### `Tetrominoes`
- Represents the tetrominoes with various shapes and their behaviors:
  - Movement (left, right, down).
  - Rotation.
  - Interaction with the grid.

#### `Tile`
- Represents individual tiles on the grid and tetrominoes.
- Handles tile merging, movement, and color updates.

#### `Button`
- Provides button functionality, such as the pause button on the game screen.

### Logic Highlights
- **Merging Tiles**:
  - Tiles in the same column merge when they have the same number.
  - Higher-numbered tiles are created based on the sum of merging tiles' values.
- **Line Clearing**:
  - Full lines are cleared, and tiles above the cleared line fall down.
- **Game Over Condition**:
  - The game ends when a tetromino cannot enter the grid due to blocked tiles.

## Prerequisites

- **Java Development Kit (JDK)**: Version 8 or higher.
- **StdDraw Library**: Ensure the `StdDraw` graphics library is included in the project. You can download it from [Princeton StdDraw Library](https://introcs.cs.princeton.edu/java/stdlib/).

## Getting Started

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/elifpulukcu/Tetris-2048.git
   ```

2. **Navigate to the Project Directory**:
   ```bash
   cd Tetris2048
   ```

3. **Compile the Java Files**:
   ```bash
   javac *.java
   ```

4. **Run the Game**:
   ```bash
   java Tetris2048
   ```

## How to Play

- Use the **arrow keys** to control the tetromino:
  - `Left Arrow`: Move left.
  - `Right Arrow`: Move right.
  - `Up Arrow`: Rotate clockwise.
  - `Down Arrow`: Speed up descent.
- Click on the "Pause" button to pause or resume the game.
- Score points by merging tiles and clearing lines.

## Customization

### Grid Dimensions
- Modify the `gridWidth` and `gridHeight` variables in the `Tetris2048` class to adjust the grid size:
  ```java
  int gridWidth = 10, gridHeight = 20; // Default is 12x20
  ```

### Tile Appearance
- Update the `numbers` and `colors` arrays in the `Tile` class to customize tile numbers and their associated colors:
  ```java
  private final static Integer[] numbers = {2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, 2048};
  private final static Color[] colors = {...};
  ```

### Game Speed
- Modify the pause duration in the main loop to adjust game speed:
  ```java
  StdDraw.pause(150); // Reduce value for faster gameplay
  ```

## Limitations

- The game grid size is fixed to 12x20 by default.
- Merging only occurs for tiles in the same column.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

Developed by [Elif Pulukçu](https://github.com/elifpulukcu).
