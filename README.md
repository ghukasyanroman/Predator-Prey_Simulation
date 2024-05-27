# Predator-Prey Simulation Project

## Disclaimer
This project was created as an educational exercise at TUMO approximately four years ago. It is intended for educational purposes only and should not be used for other applications or purposes.

## Table of Contents
1. [Overview](#overview)
2. [Files](#files)
3. [Classes](#classes)
   - [Grass](#grass)
   - [GrassEater](#grasseater)
   - [Predator](#predator)
   - [RePredator](#repredator)
   - [Rocks](#rocks)
4. [Simulation Logic](#simulation-logic)
   - [`generator(matLen, gr, grEat, st, pd, repd)`](#generatormatlen-gr-great-st-pd-repd)
   - [`setup()`](#setup)
   - [`draw()`](#draw)
5. [Notes](#notes)

## Overview
The project simulates a predator-prey ecosystem using p5.js. It includes various classes representing different entities (Grass, GrassEater, Predator, RePredator) and a matrix to manage their interactions. The simulation also includes rocks that are randomly generated each time.

## Files
- **index.html**: The HTML file that sets up the project.
- **class.js**: Contains the class definitions for Grass, GrassEater, Predator, and RePredator.
- **script.js**: Contains the main setup and draw functions to initialize and run the simulation.

### To run the code, extract the ZIP file and open the `index.html` file in a web browser. The simulation will start automatically.

## Classes
### Grass
- **Constructor**: Initializes position and directions.
- **Methods**: 
  - `chooseCell(character)`: Finds adjacent cells matching a character.
  - `mul()`: Multiplies if conditions are met.
- **Color**: Green

### GrassEater
- **Constructor**: Initializes position, energy, and directions.
- **Methods**: 
  - `getNewCoordinates()`: Updates direction coordinates.
  - `chooseCell(character)`: Finds adjacent cells matching a character.
  - `mul()`: Multiplies if conditions are met.
  - `move()`: Moves to an empty cell, losing energy.
  - `eat()`: Eats grass to gain energy.
  - `die()`: Dies when energy is depleted.
- **Color**: Yellow

### Predator
- **Constructor**: Initializes position, energy, and directions.
- **Methods**: 
  - `getNewCoordinates()`: Updates direction coordinates.
  - `chooseCell(character)`: Finds adjacent cells matching a character.
  - `mul()`: Multiplies if conditions are met.
  - `move()`: Moves to an empty cell, losing energy.
  - `eat()`: Eats grass eaters to gain energy.
  - `die()`: Dies when energy is depleted.
- **Color**: Brown

### RePredator
- **Constructor**: Initializes position and directions.
- **Methods**: 
  - `chooseCell(character)`: Finds adjacent cells matching a character.
  - `move(r)`: Moves to an empty cell. Can transform into a Predator under certain conditions.
- **Color**: Pink

### Rocks
- **Description**: Rocks are randomly generated obstacles in the matrix that entities cannot move through.
- **Color**: Black

## Simulation Logic
### `generator(matLen, gr, grEat, st, pd, repd)`
Generates a matrix of specified length and populates it with entities:
- `gr`: Number of Grass.
- `grEat`: Number of GrassEaters.
- `st`: Number of Rocks.
- `pd`: Number of Predators.
- `repd`: Number of RePredators.

### `setup()`
- Initializes canvas and frame rate.
- Fills arrays with instances of entities based on the matrix.

### `draw()`
- Updates and draws each entity on the canvas.
- Entities act (multiply, move, eat) based on their defined behaviors.
- Colors are assigned as follows:
  - **Grass**: Green
  - **GrassEater**: Yellow
  - **Predator**: Brown
  - **RePredator**: Pink
  - **Rocks**: Black
  - **Board**: Gray

## Notes
- The project uses the p5.js library for drawing.
- Entity actions are logged to the console for debugging.
