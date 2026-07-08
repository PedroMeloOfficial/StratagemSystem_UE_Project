# Assets / Starter Content

Unreal Engine 5's default Starter Content pack, used as placeholder VFX, audio, and materials for Stratagem ability effects — an explosion needs *a* particle and *a* sound before it needs a *good* one.

## Structure

| Folder | Used for |
|---|---|
| `Audio/` | `Explosion_Cue`, `Collapse_Cue`, `Fire01_Cue`, etc. — placeholder SFX referenced by ability Data Assets |
| `Materials/` | Generic surface materials (brick, concrete, wood, water, metal) — used on test environment geometry, not on Stratagem effects directly |
| `Particles/` | `P_Explosion`, `P_Fire`, `P_Smoke`, `P_Sparks`, `P_Steam_Lit` — placeholder VFX referenced by ability Data Assets |
| `Shapes/` | Basic primitive meshes (cube, sphere, cone, wedge, etc.) used for test/blockout geometry |
| `Textures/` | Supporting textures for the materials and particles above |

## Why placeholder is the right call here

Every ability's `VFX` and `SFX` fields (see [`DataAssets/StratagemAbilities`](../../Blueprints/DataAssets/StratagemAbilities/README.md)) point to assets in this folder for now. Because those fields live on the Data Asset and not hardcoded in a Blueprint, replacing `P_Explosion` with a custom effect later is a one-field change per ability — not a re-wire.
