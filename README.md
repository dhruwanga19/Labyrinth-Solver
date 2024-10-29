# Labyrinth Solver

A path finding simulator to find an exit of a maze using a modified depth first search and recursion on a undirected graph (aka the Labyrinth)

## Overview of the Simulation

### Rules

Think of the labyrinth as a set of rooms connected by corridors, some of which could be closed by walls. There are 3 types of walls:

- brick walls (displayed by the program in red)
- rock walls (displayed by the program in blue)
- metal walls

The labyrinth might not have a path to the exit; in that case the program is allowed to break some of the walls to try to reach the exit. The program is given two types of bombs to break walls:

- blast bombs (Can break brick wall, but not metal wall, requires 2 blast bombs to break rock wall)
- melt bombs (Can break a metal wall, but not brick or a rock wall)

The program will be given k_1 blast bombs and k_2 melt bombs, where k_1 and k_1 are specified in the input file.

### Map

The program will represent the labyrinth as an undirected graph. Every node of the graph corresponds to a room, and every edge corresponds to either a corridor that can be used to go from one room to the other or to a wall that the program might decide to break. There are two special nodes in this graph corresponding to the entrance and the exit.

#### Example Map (lab# files)

This is the input for the Labryrinth to draw the map

```
 S
 W
 L
 K1
 K2
 emo*obo
 |*|*|*|
 obobo-o
 **R*|*|
 o-o-xbo
```

Each one of the first five lines contain one number: S, W, L, K1, or K2.

- S is the scale factor used to display the labyrinth on the screen.
- W is the width of the labyrinth. The rooms of the labyrinth are arranged in a grid. The number of rooms in each row of this grid is the width of the labyrinth.
- L is the length of the labyrinth, or the number of rooms in each column of the grid.
- K1 is the number of blast bombs that the program is allowed to use while looking for a solution.
- K2 is the number of melt bombs that the program is allowed to use while looking for a solution.
- For the rest of the file, the meaning of the characters is as follows:
  - ’e’: entrance to the labyrinth
  - ’x’: exit of the labyrinth
  - ’o’: room
  - ’b’:horizontalbrickwall
  - ’r’:horizontalrockwall
  - ’m’:horizontalmetalwall
  - ’B’:verticalbrickwall
  - ’R’:verticalrockwall
  - ’M’:verticalmetalwall
  - ’-’:horizontalcorridor
  - ’|’:verticalcorridor
  - ’\*’:unbreakable,solidstoneblock

There is only one entrance and one exit, and each line of the file (except the first four lines) must have the same length.
