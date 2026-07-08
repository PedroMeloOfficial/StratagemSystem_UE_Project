# Stratagem Abilities / Ravens

Fast, offensive strike-type Stratagems — short delay, single sharp effect. The family name is a deliberate departure from the "Eagle" naming used by Helldivers 2's equivalent category, to keep the system's naming clear of that game's trademarked terms (see the project root README for context on this decision).

## `PDA_Stratagem_Ravens`

The typed Data Asset subtype for this family. Extends `PDA_Stratagem_BASE` with whatever fields are specific to fast air-strike-style abilities (e.g. impact radius, spread).

## Instances

| Data Asset | Spawns | Notes |
|---|---|---|
| `DA_RavenSmokeStrike` | `BP_StratagemAbility_SmokeStrike` | Smoke cloud for area denial / vision blocking |
| `DA_RavenTomahawkStrike` | `BP_StratagemAbility_AirStrike` | Direct offensive strike |

> **Adding a new Raven:** right-click `PDA_Stratagem_Ravens` → **Create Data Asset**. Point it at an existing `BP_StratagemAbilityBASE` subclass if the behavior already exists (as `DA_RavenSmokeStrike` does), or create a new subclass under [`Actors/Abilities`](../../../Actors/Abilities/README.md) if it doesn't.
