# Actors / Abilities

The classes that get spawned when a Stratagem resolves. This is where the actual gameplay effect lives — the explosion, the sentry, the smoke cloud.

## `BP_StratagemAbilityBASE`

The parent of every ability in the system. It holds a reference to its own `PDA_Stratagem_BASE` Data Asset (see [`DataAssets/StratagemAbilities`](../../DataAssets/StratagemAbilities/README.md)) and exposes the shared beacon-to-effect pipeline: land, wait `DelayDuration`, resolve.

What the base class handles for you:
- Reading `DelayDuration`, `SFX`, and `VFX` from its Data Asset — you never hardcode these in a subclass
- The beacon landing callback
- Broadcasting deployment events back to `BPC_StratagemSystem`

What a subclass is responsible for:
- Overriding the resolve function with whatever this specific ability actually *does*

> **This split is the whole point of the architecture.** Programming a new ability should only ever mean writing the resolve logic — never re-wiring delay timers, sound, or particles. Those come from the Data Asset for free.

## Current abilities

| Blueprint | What it does |
|---|---|
| `BP_StratagemAbility_AirStrike` | Area damage at the beacon location |
| `BP_StratagemAbility_SmokeStrike` | Deploys a smoke cloud at the beacon location for area denial / vision blocking |

## `Sentrys/`

Sentry-type abilities get their own base class before the concrete implementation, because turrets need behavior (targeting, firing) that a one-shot explosion doesn't:

| Blueprint | What it does |
|---|---|
| `BP_StratagemAbility_Sentry_Base` | Shared turret behavior — target detection, rotation, firing loop |
| `BP_StratagemAbility_LightMachineGunSentry` | Concrete sentry using the base's targeting loop with LMG-specific fire rate and damage |

> **Adding a new sentry?** Subclass `Sentry_Base`, not `BP_StratagemAbilityBASE` directly — you'll inherit the targeting and firing loop instead of rebuilding it.
