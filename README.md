# PacMan Game in Java (2D)

This is a **2D PacMan game built using Java and Swing**, created as a personal project to replicate the classic PacMan arcade game. 
The game uses tile-based movement, collision detection, ghost AI, and score tracking.

---

## Game Overview

The game board consists of:

* **21 rows × 19 columns**
* **Tile size:** 32 × 32 pixels
* **Board size:** 608 × 672 pixels
* Built using **Java Swing and AWT**
* Uses a **tile-map system** to generate walls, food, ghosts, and PacMan

Each tile represents an element:

```
X = Wall
' ' = Food
P = PacMan spawn
b = Blue Ghost
r = Red Ghost
p = Pink Ghost
o = Orange Ghost
O = Skip / empty tunnel
```

---

##  Game Features

* Smooth PacMan movement
* Tile-based map system
* Ghost AI with random movement
* Collision detection system
* Score tracking
* Lives system
* Game Over and restart system
* Automatic map reload after clearing all food

---

## Controls

| Key | Action     |
| --- | ---------- |
| ↑   | Move Up    |
| ↓   | Move Down  |
| ←   | Move Left  |
| →   | Move Right |

---

## Project Structure

```
pacman/
│
├── src/
│   ├── App.java
│   └── PacMan.java
│
├── assets/
│   ├── wall.png
│   ├── blueGhost.png
│   ├── redGhost.png
│   ├── pinkGhost.png
│   ├── orangeGhost.png
│   ├── pacmanUp.png
│   ├── pacmanDown.png
│   ├── pacmanLeft.png
│   └── pacmanRight.png
│
├── README.md
└── .gitignore
```

---

## How the Game Works (Technical Explanation)

### Tile Map System

The game uses a String array map:

```
21 rows × 19 columns
```

Each character represents an object.

The map is parsed and converted into game objects using:

```
HashSet<Block> walls
HashSet<Block> ghosts
HashSet<Block> foods
Block pacman
```

---

### Game Loop

The game runs using a Swing Timer:

```
Timer gameLoop = new Timer(45, this);
```

Which handles:

* Movement updates
* Collision detection
* Rendering
* Score updates

---

### Collision Detection

Uses rectangle collision logic:

```
a.x < b.x + b.width &&
a.x + a.width > b.x &&
a.y < b.y + b.height &&
a.y + a.height > b.y
```

---

### Ghost AI

Ghosts use the A (A-Star) pathfinding algorithm* to intelligently chase PacMan.

Instead of moving randomly, each ghost:

Converts its pixel position into grid coordinates

Calculates the shortest path to PacMan using A*

Uses a priority queue with the function:

f(n) = g(n) + h(n)

Where:

g(n) = distance from ghost to current tile

h(n) = Manhattan distance heuristic to PacMan

This ensures:

Optimal shortest path

Fast computation suitable for real‑time gameplay

Efficient navigation around walls

This makes ghost behavior intelligent and similar to classic PacMan AI.

Performance complexity:

Time Complexity: O(V log V)

Which is extremely fast for a 21 × 19 grid.

---

## How to Run

Open terminal inside project folder:

Compile:

```
javac src/*.java
```

Run:

```
java -cp src App
```

---

## Technologies Used

* Java
* Java Swing
* Java AWT
* Object-Oriented Programming
* Tile-based game design

---

## Learning Purpose

This project helped practice:

* Game development fundamentals
* Java Swing graphics
* Collision detection
* Game loops
* Object-oriented design

---

## Future Improvements

Possible upgrades:

* Smarter ghost AI
* Animations
* Sound effects
* Multiple levels
* Main menu
* Power pellets

---
---
