# Assets / UI

Icon textures used by the HUD (see [`Blueprints/Widgets`](../../Blueprints/Widgets/README.md)).

## `Textures/`

| Texture | Used for |
|---|---|
| `arrowUp`, `arrowDown`, `arrowLeft`, `arrowRight` | Directional input feedback in `WB_ArrowBox` — one arrow lights up per accepted input in a sequence |
| `BombIcon` | Icon for offensive/strike-type Stratagems |
| `SmokeIcon` | Icon for the Smoke Strike ability |
| `turretIcon` | Icon for Sentry-type Stratagems |

Each ability's `PDA_Stratagem_BASE` instance (see [`DataAssets/StratagemAbilities`](../../Blueprints/DataAssets/StratagemAbilities/README.md)) references one of these icons directly — the HUD never hardcodes which icon belongs to which ability.
