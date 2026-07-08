# Content/StratagemSystem

Everything for the project lives under this single folder. That's intentional — it's what makes the system portable.

> **Migration rule:** if you ever need to move this system into another UE5 project, you should be able to migrate this `StratagemSystem` folder on its own. If a migration pulls in content from outside it, something references outside the system and should be fixed first. Use **Reference Viewer** on this folder before migrating to confirm.

## Folder Map

| Folder | What it is |
|---|---|
| [`Blueprints/`](Blueprints/README.md) | The system's logic — components, abilities, Data Assets, interfaces, HUD widgets |
| [`Inputs/`](Inputs/README.md) | Enhanced Input Actions and Mapping Contexts |
| [`Assets/`](Assets/README.md) | Meshes, materials, textures, audio (mostly placeholder) |
| [`Demo/`](Demo/README.md) | The playable test environment — **not** part of the reusable system |

If you're trying to understand *how the system works*, start in `Blueprints/`. If you're trying to *play* the demo, start in `Demo/`.
