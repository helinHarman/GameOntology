# Design Decisions & Ontology Axioms

This document outlines the logical constraints, modeling choices, and axioms implemented in the "Semantic Skeleton" game ontology to ensure data integrity and consistency.

## 1. Structural Axioms (Mandatory Requirements)

### Decision: The Character Mandate
- **Constraint:** `Character SubClassOf (equippedWith some Weapon)`
- **Rationale:** To fulfill the "Combat Readiness" requirement. A character without a weapon cannot function within the game's combat mechanics.
- **Implementation:** Added as a formal class restriction in Protégé.

### Decision: Ownership Constraint
- **Constraint:** `Character SubClassOf (belongsTo exactly 1 Player)`
- **Rationale:** Prevents "orphaned" characters. Every character must be linked to a single unique player account to maintain accountability and data ownership.

## 2. Relationship Modeling

### Decision: Inverse Property Implementation
- **Description:** Defined `hasCharacter` as the Inverse Property of `belongsTo`.
- **Rationale:** This allows for bidirectional queries. If we know the Player, we can find the Character, and if we have the Character, we can identify the Player without extra coding.

### Decision: Transitive Property for Item Hierarchy
- **Description:** Defined `partOf` as a Transitive Property for complex items.
- **Rationale:** If a 'Scope' is part of a 'Sniper Rifle', and the 'Sniper Rifle' is part of the 'Player Inventory', the system automatically infers that the 'Scope' is also part of the 'Player Inventory'.

## 3. Data Integrity & Domain Rules

### Decision: Functional Property for Levels
- **Constraint:** `hasLevel` defined as a Functional Property.
- **Rationale:** A character or player cannot have two different levels simultaneously. This ensures that the progression state is always a single, consistent value.

### Decision: Disjoint Classes for Items
- **Description:** `Weapon` and `Armor` are defined as Disjoint Classes.
- **Rationale:** Logic enforcement—an item cannot be both a defensive armor and an offensive weapon at the same time. This prevents classification errors during the reasoning process.

## 4. Quest and Achievement Logic

### Decision: Property Chain for Rewards
- **Description:** Created a property chain: `completesQuest o givesReward -> earnsAchievement`.
- **Rationale:** Automatically grants an achievement to the player once the reasoning engine detects the completion of a specific quest that offers a reward.

---
*Last Modified: April 27, 2026*
