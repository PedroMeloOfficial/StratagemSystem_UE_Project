# Data Assets / Stratagem Types

Answers one question only: **what category is this Stratagem, and what color represents it in the UI?**

This is intentionally separate from the ability *family* (`Ravens`, `Sentrys`, etc. — see [`StratagemAbilities/`](../StratagemAbilities/README.md)). A family is about *what kind of thing this ability is*; a Type is about *how the UI should categorize and color it*. Multiple families can share the same Type.

## `PDA_StratagemType`

The base Data Asset. Holds:
- `TypeName` (e.g. "Attack")
- `TypeColor` — displayed behind the Stratagem's icon in the HUD

## Instances

| Data Asset | Category |
|---|---|
| `DA_ST_Attack` | Offensive Stratagems |
| `DA_ST_Defense` | Defensive Stratagems (e.g. Sentries) |
| `DA_ST_AreaControl` | Stratagems that control space rather than dealing damage directly (e.g. smoke) |

> **Adding a new category:** right-click `PDA_StratagemType` → **Create Data Asset**, give it a name and a color, then reference it from any `PDA_Stratagem_BASE` subtype instance. No Blueprint or UI code needs to change — the HUD reads the color directly from whichever Type is assigned.
