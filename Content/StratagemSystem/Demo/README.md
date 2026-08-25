# Demo

A small playable environment used to test the Stratagem System end to end. This folder is **not** part of the reusable system — if you migrate this project's system into another game, leave `Demo/` behind.

> **Why this is separated from `Blueprints/`:** a buyer/integrator of this system shouldn't need a dummy target or a main menu — they need the component, the abilities, and the Data Assets. Keeping the demo in its own folder means the core system can be migrated on its own (see the root README's migration note).

## Subfolders

| Folder | Contents |
|---|---|
| [`DummyTarget/`](DummyTarget/README.md) | A damageable target used to playtest offensive Stratagems |
| [`Maps/`](Maps/README.md) | The demo's levels — main menu and test arena |
| [`Widgets/`](Widgets/README.md) | The demo's main menu UI |

## Quick start

Open `Maps/Stratagem_Gym.umap`, possess `BP_Player`, and hold **Open Stratagem** to try the input sequence system against the dummy targets placed in the level.
