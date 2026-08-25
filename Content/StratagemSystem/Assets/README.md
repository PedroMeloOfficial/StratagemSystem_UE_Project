# Assets

Visual and audio assets used by the demo and by the ability effects. This project deliberately prioritizes **systems programming over art** — almost everything here is either Unreal's own default content or a simple placeholder, not custom-made art.

> **If you're evaluating this project as a portfolio piece:** the value is in `Content/StratagemSystem/Blueprints`, not in this folder. Nothing here was built to look good — it was built to not get in the way of testing the system.

## Subfolders

| Folder | What it is |
|---|---|
| [`Mannequins/`](Mannequins/README.md) | Unreal's default 5th-generation Manny/Quinn character — used as the demo's player character |
| [`StarterContent/`](StarterContent/README.md) | Unreal's default Starter Content pack — generic materials, particles, audio |
| [`Turret/`](Turret/README.md) | Placeholder skeletal mesh for the Sentry ability |
| [`UI/`](UI/README.md) | Icons for Stratagem types and directional input feedback |
| [`Weapons/`](Weapons/README.md) | Placeholder weapon meshes (Pistol, Rifle, Grenade Launcher) for the demo character |

None of this is referenced directly by the core system logic — a `PDA_Stratagem_BASE` instance points to whatever mesh/texture/sound you assign it. Swapping any asset here for better art requires no Blueprint changes.
