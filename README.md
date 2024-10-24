# Conway's Game of Life: Gosper's Glider Gun Animation

## Overview
This project implements Conway's Game of Life using Python, focusing on the behavior of the Gosper's Glider Gun. The glider gun is a well-known pattern that produces an infinite number of gliders, which are another type of oscillating pattern. The simulation utilizes NumPy for numerical computations, Matplotlib for visualization, and creates an animation to illustrate the glider's behavior over time.

## Requirements
To run this project, you need the following Python packages:
- NumPy
- Matplotlib

## Description of the Code

### Initial Setup
The simulation grid is initialized with a size of 38 rows and 58 columns. The state of each cell is represented as a 2D NumPy array called `life`, where:
- `0` indicates a dead cell
- `1` indicates a living cell

The initial configuration for the Gosper's Glider Gun is set up within this grid, allowing it to create and emit gliders.

### Neighbor Calculation
A helper function, `nneighbors`, is defined to calculate the number of living neighbors for a given cell. This function checks the eight surrounding cells and counts how many of them are alive, taking into account the grid boundaries to avoid index errors.

### Game State Update
The `step` function updates the state of the game for all cells in the grid based on the following rules:
- Any live cell with two or three live neighbors survives to the next generation.
- Any dead cell with exactly three live neighbors becomes a live cell.
- All other live cells die in the next generation.

The updated states are stored in a temporary array, which is then used to update the global variable representing the game's current state.

### Animation
The `update` function is called for each frame of the animation, executing the `step` function and updating the visualization. The animation is saved as an HTML file, allowing for easy viewing in a web browser.
