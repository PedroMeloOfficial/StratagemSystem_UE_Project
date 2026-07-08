# Stratagem Abilities / Sentrys

Deployed, persistent Stratagems — rather than resolving once like a strike, a Sentry spawns an actor that keeps acting (targeting and firing) until it's destroyed or expires.

## `PDA_Stratagem_Sentrys`

The typed Data Asset subtype for this family. Extends `PDA_Stratagem_BASE` with fields a one-shot strike doesn't need — targeting range, rotation speed, fire rate — matching the behavior implemented in [`BP_StratagemAbility_Sentry_Base`](../../../Actors/Abilities/README.md).

## Instances

| Data Asset | Spawns | Notes |
|---|---|---|
| `DA_LightMachineGunSentry` | `BP_StratagemAbility_LightMachineGunSentry` | Automated turret with LMG fire rate/damage |

> **Known issue:** the Sentry ability is currently the least stable part of the system — it was deprioritized while the Data Asset hierarchy refactor was in progress. Verify targeting and firing behavior end-to-end before relying on it for a demo or submission.

> **Adding a new Sentry:** subclass `BP_StratagemAbility_Sentry_Base` (not `BP_StratagemAbilityBASE` directly) so you inherit the targeting/firing loop, then create a matching `PDA_Stratagem_Sentrys` instance pointing to your new subclass.
