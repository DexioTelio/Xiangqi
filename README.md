# Xiangqi Engine (C#)

A rule‑based engine for the board game Xiangqi (Chinese Chess) implemented in C#. This project focuses on modeling the rules and domain of the game rather than providing a graphical interface.

The goal is to build a clean, maintainable, and testable implementation of the game mechanics. It is designed as a learning project and a portfolio piece demonstrating software engineering practices such as domain modeling, object‑oriented design, and automated testing.

---

# Project Goals

* Implement the core rules of Xiangqi.
* Design a clean domain model.
* Practice C# and .NET ecosystem tools.
* Build a well‑tested rule engine.
* Explore good software architecture practices.

The project intentionally excludes any graphical interface so that the focus remains on the domain logic.

---

# Scope

## Included

* Board representation (9×10 grid intersections)
* Piece representation
* Initial game setup
* Legal move generation
* Move execution
* Capture rules
* Check detection
* Checkmate detection
* Special rules of Xiangqi

## Not Included

* GUI
* Networking or multiplayer servers
* Advanced AI

These may be added later as extensions.

---

# Game Overview

Xiangqi is a two‑player strategy board game similar to Western chess but with different pieces and rules.

Key characteristics:

* The board has **9 files and 10 ranks**.
* Pieces are placed on **intersections**, not squares.
* A **river** divides the two sides of the board.
* Each player has a **palace** (3×3 area) restricting certain pieces.

Each player begins with **16 pieces**:

* 1 General
* 2 Advisors
* 2 Elephants
* 2 Horses
* 2 Chariots
* 2 Cannons
* 5 Soldiers

The objective is to **checkmate the opposing General**.

---

# Architecture

The project is organized around a domain‑driven structure.

```
Xiangqi
│
├─ Domain
│   ├─ Game
│   ├─ Board
│   ├─ Position
│   ├─ Move
│   └─ Pieces
│
├─ Rules
│   ├─ MovementRules
│   └─ GameRules
│
├─ Engine
│   └─ MoveGenerator
│
└─ Tests
```

## Domain

Contains the core game model.

Core entities:

* **Game** – manages turns and overall state
* **Board** – represents the game board and piece placement
* **Position** – value object representing coordinates
* **Piece** – base type for all pieces
* **Move** – represents a move action

## Pieces

Each piece type encapsulates its movement logic.

Types:

* General
* Advisor
* Elephant
* Horse
* Chariot
* Cannon
* Soldier

---

# Special Rules

Xiangqi contains several rules that influence the design of the engine:

* The **General and Advisors** must remain inside the palace.
* **Elephants cannot cross the river**.
* **Horses can be blocked** if the adjacent square is occupied.
* **Cannons capture by jumping exactly one piece**.
* The two **Generals may not face each other directly** on the same file without a piece in between.

These rules are implemented as explicit validation logic in the engine.

---

# Testing

Testing is a central part of the project.

Examples of test cases:

* General cannot leave palace
* Elephant cannot cross the river
* Horse blocked movement
* Cannon capture rules
* Generals cannot face each other
* Check detection
* Checkmate detection

The test suite ensures correctness and helps maintain confidence when refactoring the engine.

---

# Possible Future Extensions

Potential improvements for future versions:

* Command Line Interface (CLI)
* AI opponent (minimax / alpha‑beta pruning)
* Game notation parser
* REST API for remote play
* Generic board game engine

---

# Purpose of the Project

This repository exists primarily for:

* learning C#
* practicing domain modeling
* improving software design skills
* building a strong backend‑style portfolio project

It is intentionally focused on **clarity of design and correctness of rules** rather than visual presentation.

---

# License

MIT License
