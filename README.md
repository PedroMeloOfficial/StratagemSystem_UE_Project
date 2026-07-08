# Stratagem System

A modular, data-driven tactical support system for Unreal Engine 5, inspired by the Stratagem mechanic in Helldivers 2 created by **Pedro Melo**.

Players enter directional input sequences to call in support abilities — airstrikes, sentry turrets, supply drops, and more — each fully configured through Data Assets rather than hardcoded Blueprint logic.

> **This is a system, not a game.** The project ships with a small demo (map, dummy target, main menu) so the system can be tested end to end, but the demo is not the product. The product is the framework under `Content/StratagemSystem/Blueprints` — the input pipeline, the typed Data Asset hierarchy, and the ability base classes it's built around.

---

## What's inside

| Folder | Purpose |
|---|---|
| [`Content/StratagemSystem/Blueprints`](Content/StratagemSystem/Blueprints/README.md) | The system itself — components, ability classes, Data Assets, interfaces, HUD |
| [`Content/StratagemSystem/Inputs`](Content/StratagemSystem/Inputs/README.md) | Enhanced Input Actions and Mapping Contexts driving the input sequence |
| [`Content/StratagemSystem/Assets`](Content/StratagemSystem/Assets/README.md) | Meshes, materials, textures and audio — mostly placeholder / Starter Content |
| [`Content/StratagemSystem/Demo`](Content/StratagemSystem/Demo/README.md) | Playable demo used to test the system — not part of the reusable framework |

Each folder above has its own `README.md` going into more detail. Start with the Blueprints one if you only read one file.

---

## Getting Started

1. Open `UE_StratagemSystem.uproject` in Unreal Engine 5.
2. Open `Content/StratagemSystem/Demo/Maps/Stratagem_Gym.umap` to try the system in a live test arena.
3. Hold the **Open Stratagem** input, enter a directional sequence, then throw — see [`Blueprints/Components`](Content/StratagemSystem/Blueprints/Components/README.md) for exactly how that pipeline works.
4. To add a new ability, see the **Extending the System** section in [`Blueprints/DataAssets/StratagemAbilities`](Content/StratagemSystem/Blueprints/DataAssets/StratagemAbilities/README.md).

---

## Project Info

- **Engine:** Unreal Engine 5
- **Primary language:** Blueprint
- **Author:** Pedro Melo
- **License:** See `LICENSE`
