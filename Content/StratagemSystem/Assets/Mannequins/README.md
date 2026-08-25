# Assets / Mannequins

Unreal Engine 5's default 5th-generation Manny and Quinn character assets, used unmodified as the demo's player character. Standard content from the Third Person / First Person template — nothing here is custom.

## Structure

| Folder | Contents |
|---|---|
| `Anims/` | Animations grouped by weapon context: `Pistol/`, `Rifle/`, `Unarmed/`, plus shared `Death/` and `Rifle/HitReact/` |
| `Materials/` | `Manny/` and `Quinn/` material instances |
| `Meshes/` | `SK_Mannequin`, `SKM_Manny_Simple`, `SKM_Quinn_Simple` |
| `Rigs/` | Control Rig assets (`CR_Mannequin_Body`, `CR_Mannequin_FootIK`, `CR_Mannequin_Procedural`) and the shared Physics Asset (`PA_Mannequin`) |
| `Textures/` | `Manny/`, `Quinn/`, and `Shared/` texture sets |

## Why it's here unmodified

The demo character exists only to give `BPC_StratagemSystem` something to attach to and to give the player hands/arms holding a weapon while testing Stratagems. There was no reason to customize it — any project integrating this system will already have its own character art.

> **Not part of the system.** If you migrate `Content/StratagemSystem/Blueprints` into another project, you don't need this folder at all.
