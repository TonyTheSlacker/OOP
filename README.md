# C++ Console RPG: Battle System

![Language](https://img.shields.io/badge/Language-C++-00599C?logo=c%2B%2B&logoColor=white)
![Paradigm](https://img.shields.io/badge/Paradigm-Object--Oriented-orange)
![Status](https://img.shields.io/badge/Status-Educational-green)

A turn-based role-playing game (RPG) engine running in the console. This project serves as a practical demonstration of **Object-Oriented Programming (OOP)** in C++, featuring a modular class hierarchy, runtime polymorphism, and dynamic character casting.

Players can choose between **PvP (Player vs. Player)** or **PvE (Player vs. Environment)** modes, utilizing unique skills, leveling up, and managing resources (HP/SP).

---

## 🗝️ Key Features

### ⚔️ Game Modes
* **PvE Campaign:** Infinite survival mode against randomized enemies (Slimes, Dragons, and even Gods).
* **PvP Duel:** Local multiplayer allowing two players to pit different classes against each other.

### 🛡️ Class System (Polymorphism)
Three distinct character classes derived from a base abstract class, each with unique stats and abilities:
* **Knight:** High HP/Strength. Abilities: *Power Slash, Shield Block*.
* **Wizard:** High Magic. Abilities: *Fireball, Light of Justice*.
* **Assassin:** High Agility/Strength. Abilities: *Deep Cut, Stealth*.

### 📈 Progression System
* **Leveling Mechanics:** XP gain system that scales stats (Strength/Magic) by 20% upon leveling up.
* **Resource Management:** Tactical use of Potions and Skill Points (SP) is required to survive longer battles.

---

## 🛠️ Technical Implementation

### 1. OOP Architecture
The system uses a robust inheritance structure to share logic while allowing unique behaviors.
* **Base Class:** `Character` (Abstract Class with pure virtual functions).
* **Derived Classes:** `Knight`, `Wizard`, `Assassin`.
* **Polymorphism:** The `action()` and `useSkill()` methods are overridden to provide unique gameplay for each class.

### 2. Dynamic Casting & RTTI
The battle loop uses `dynamic_cast` to safely determine the specific subclass of a character pointer at runtime, allowing for class-specific logic within a generic loop.

```cpp
// Snippet from battlePVE function
if (auto knight = dynamic_cast<Knight*>(&player)) {
    damage = knight->action();
}
else if (auto wizard = dynamic_cast<Wizard*>(&player)) {
    damage = wizard->action();
}
```

### 3. Memory Management

    Uses pointers (Character* player) to manage polymorphic objects.

    Explicit delete calls ensure no memory leaks occur when characters are destroyed after battle.

## 🚀 How to Run
  1. Clone the repository:
    ```
      git clone https://github.com/TonyTheSlacker/OOP.git```
  2. Open Project:
    Open the .sln file in Visual Studio.

  3. Compile & Run:
    Press F5 (or click "Local Windows Debugger").

  **Compatibility: The code uses standard C++ libraries (<iostream>, <vector>, <string>) and is cross-compatible, though system("cls") is optimized for Windows.**
