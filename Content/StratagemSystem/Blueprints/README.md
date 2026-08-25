# Blueprints

This is the Stratagem System itself. Everything the system needs to function — independent of any specific game — lives in this folder.

## How the pieces fit together

```
Player holds "Open Stratagem"
        │
        ▼
BPC_StratagemSystem (Components/)     ── owns input state, cooldowns, registered Stratagems
        │
        ├─ reads sequence against  →  PDA_StratagemInput instances (DataAssets/StratagemInputs/)
        │
        ├─ on match, resolves      →  a PDA_Stratagem_BASE subtype (DataAssets/StratagemAbilities/)
        │                              which points to...
        │
        └─ spawns                 →  a BP_StratagemAbilityBASE subclass (Actors/Abilities/)
                                       which does the actual work (explosion, sentry, etc.)

BP_HUD_StratagemSystem (Widgets/) listens to the component's events to draw input feedback,
cooldowns, and the Stratagem Type color — using BPI_GetPDAStratagem and BPI_GetHudWidget
(Interfaces/) to talk to the component without a hard reference.
```

## Subfolders

| Folder | Contents |
|---|---|
| [`Components/`](Components/README.md) | `BPC_StratagemSystem` — the single component that runs the whole system |
| [`Actors/Abilities/`](Actors/Abilities/README.md) | The ability classes — what actually happens when a Stratagem resolves |
| [`Actors/Characters/`](Actors/Characters/README.md) | The demo's Player and base Character Blueprints hosting the component |
| [`DataAssets/`](DataAssets/README.md) | Every configurable value in the system — sequences, cooldowns, types, VFX/SFX |
| [`Interfaces/`](Interfaces/README.md) | Blueprint Interfaces used to keep the system decoupled from any one Character |
| [`Helpers/`](Helpers/README.md) | GameMode, GameInstance, PlayerController, and CameraManager for the demo |
| [`Widgets/`](Widgets/README.md) | The HUD — input feedback, cooldown display, Stratagem selection |

## Where to start reading

1. **`Components/BPC_StratagemSystem`** — the entry point. If you understand this component, you understand the system.
2. **`DataAssets/StratagemAbilities/`** — how a new ability gets added without touching Blueprint logic.
3. **`Actors/Abilities/BP_StratagemAbilityBASE`** — the one class every ability extends.

> **Rule of thumb while extending this system:** if you find yourself hardcoding a value that's specific to one ability (a cooldown, a radius, a sound), it belongs in a Data Asset, not in the Blueprint graph. Keep the Blueprint responsible for *behavior*, and the Data Asset responsible for *configuration*.
