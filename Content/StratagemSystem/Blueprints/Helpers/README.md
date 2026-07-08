# Helpers

Framework-level Blueprints needed to run the demo — GameMode, GameInstance, PlayerController, CameraManager. None of this is part of the reusable Stratagem System itself; it's scaffolding the demo needs to run as a standalone project.

| Blueprint | Role |
|---|---|
| `GM_StratagemSystem` | GameMode — spawns `BP_Player` as the default pawn for the demo |
| `GI_StratagemSystem` | GameInstance — persists data across level loads (e.g. Main Menu → Stratagem Gym) |
| `BP_StratagemSystemController` | PlayerController — routes input to the possessed Pawn |
| `BP_StratagemSystemCameraManager` | Camera manager for the demo's player camera |

> **If you're integrating the system elsewhere:** you almost certainly already have your own GameMode, GameInstance, and PlayerController. You don't need to adopt any of these — just make sure your own PlayerController (or Pawn) implements the interfaces listed in [`Interfaces/`](../Interfaces/README.md).
