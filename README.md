# The Semantic Skeleton: Architecting a Video Game Universe

This project, developed for the **CSE 3226 Knowledge Engineering and Ontology** course, presents a comprehensive gaming ontology designed to model the complex relationships within a video game ecosystem. Using the "Semantic Skeleton" approach, it transforms isolated data points into a fully navigable, machine-readable environment.

## 📌 Project Objectives
The aim of this ontology is to define explicit relationships between players, characters, items, and quests. It allows for:
* Hierarchical classification of in-game entities.
* Semantic analysis of player interactions and achievements.
* Enforcement of logical game rules through mathematical axioms.

## 🛠 Technologies and Standards
* **Ontology Language:** OWL (Web Ontology Language)
* **Development Tool:** Protégé 5.5.0
* **Reasoning:** HermiT / Pellet (for logical consistency)
* **Implementation:** Java 8 (JRE 1.8)

## 🏗 Ontology Architecture
The "Semantic Skeleton" is built upon several core pillars:

### 1. Core Entities (Classes)
Every entity in this universe stems from `owl:Thing`:
* **Player:** The human user behind the screen.
* **Character:** The digital avatar within the game world.
* **Game:** The virtual environment (e.g., CounterStrike, PUBG).
* **Item:** In-game objects, further classified into **Armor** and **Weapon**.
* **Quest:** Objectives and challenges to conquer.
* **Achievement:** Trophies signifying player success.

### 2. Defining Relationships (Object Properties)
* `plays`: Links a **Player** to a **Game**.
* `hasCharacter`: Links a **Player** to their **Character** (Inverse of `belongsTo`).
* `equippedWith` / `wears`: Defines the items a **Character** uses.
* `completesQuest` / `earnsAchievement`: Tracks player progression and rewards.

### 3. Data Properties (Assigning Values)
* `hasDamage`: Numerical output for weapons.
* `hasLevel`: Quantifiable progression state for characters.
* `hasDifficulty`: Rating for quests (e.g., Hard, Easy).
* `hasUsername`: Unique handles for players.

## ⚖️ The Laws of the Universe (Axioms)
The ontology enforces logical game rules:
1. **Existence:** A Character cannot exist independently; it *must* belong to a Player.
2. **Combat Readiness:** A Character cannot enter the world unarmed; it *must* have a weapon.
3. **Progression:** A Character must have a quantifiable progression state (`hasLevel some owl:rational`).

## 📂 Repository Structure
* `/src`: Source ontology files (`.owl`, `.rdf`).
* `/docs`: Ontology Requirements Specification Document (ORSD) and design decision logs.
* `/presentation`: "The Semantic Skeleton" slides and visual graphs.

## 🚀 How to Run
1. Download and install [Protégé](https://protege.stanford.edu/).
2. Open the `.owl` file from the `/src` directory.
3. Start the reasoner (HermiT) to verify the consistency of the logical axioms.
