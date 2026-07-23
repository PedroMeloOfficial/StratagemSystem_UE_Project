# Data Assets / Stratagem Abilities

The core data hierarchy of the whole system. This used to be a single flat `PDA_Stratagem` holding every variable for every ability type — it's now a typed hierarchy where each family only exposes the fields relevant to it.

## `PDA_Stratagem_BASE`

The root class. Fields every Stratagem needs regardless of family:

- Display name, description, icon
- Input sequence (which `PDA_StratagemInput` combination triggers it)
- Cooldown
- Reference to its `PDA_StratagemType` (for UI color and categorization)
- `DelayDuration`, `SFX`, `VFX` — read by `BP_StratagemAbilityBASE` at deployment

## The families

Each subfolder is a family with its own typed subtype of `PDA_Stratagem_BASE`, plus individual instances configured for specific abilities:

| Family | Type asset | Instances | Corresponds to |
|---|---|---|---|
| [`Ravens/`](Ravens/README.md) | `PDA_Stratagem_Ravens` | `DA_RavenSmokeStrike`, `DA_RavenTomahawkStrike` | Fast offensive air strikes |
| [`Starfalls/`](Starfalls/README.md) | `PDA_Stratagem_Starfall` | *(none configured yet)* | Slower, heavier orbital-style bombardment |
| [`Sentrys/`](Sentrys/README.md) | `PDA_Stratagem_Sentrys` | `DA_LightMachineGunSentry` | Deployed automated turrets |
| [`Supplys/`](Supplys/README.md) | `PDA_Stratagem_Supplys` | *(none configured yet)* | Resupply / utility drops |
| [`Rogues/`](Rogues/README.md) | `PDA_Stratagem_Rogues` | *(none configured yet)* | Reserved — not yet implemented |

## Extending the system — adding a new Stratagem

This is the workflow the whole architecture is built around:
<img width="1038" height="270" alt="image" src="https://github.com/user-attachments/assets/355efbc1-c354-4574-b52c-5e372122a14c" />


1. **Adding an ability to an existing family?** Right-click the family's type asset (e.g. `PDA_Stratagem_Ravens`) → **Create Data Asset** to make a new instance. Fill in its sequence, cooldown, delay, SFX/VFX, and pick which `BP_StratagemAbilityBASE` subclass it spawns.
2. **Adding a whole new family?** Create a new subtype of `PDA_Stratagem_BASE` with whatever extra fields that family needs (see `Sentrys/` for an example of a family with family-specific fields like targeting range).
3. Either way, **no existing Blueprint graph should need to change.** If it does, something in the new ability isn't actually configuration — it's behavior, and belongs in a `BP_StratagemAbilityBASE` subclass instead.
<img width="197" height="422" alt="image" src="https://github.com/user-attachments/assets/1f27f548-cc2d-4e80-a7de-6500066fbb41" />
<img width="609" height="277" alt="image" src="https://github.com/user-attachments/assets/0d5399bb-c875-438e-b76f-d4283d1944a8" />
<img width="1060" height="663" alt="image" src="https://github.com/user-attachments/assets/bf4a3ff4-bf49-4ff9-aa67-f9c4fa5b8aba" />


> **Why this refactor was worth it:** before this hierarchy existed, every Stratagem's Data Asset carried fields for every other family too — a Sentry's data asset had unused smoke-radius fields, and vice versa. Splitting by family means each one only shows what's actually relevant, and there's no way to misconfigure an unrelated type.
