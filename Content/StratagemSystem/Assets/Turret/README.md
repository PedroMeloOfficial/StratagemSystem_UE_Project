# Assets / Turret

Placeholder skeletal mesh used by the Sentry ability family.

| Asset | Purpose |
|---|---|
| `turretTest` | Skeletal mesh for the deployed sentry |
| `turretTest_Skeleton` | Its skeleton, needed for the rotation/aiming bones the targeting logic drives |
| `turretTest_PhysicsAsset` | Physics Asset for collision |

Used by `BP_StratagemAbility_LightMachineGunSentry` (see [`Blueprints/Actors/Abilities`](../../Blueprints/Actors/Abilities/README.md)) — the base/turret rotation bone here is what `BP_StratagemAbility_Sentry_Base`'s targeting logic actually rotates each frame.

> **Test asset, name and all.** This is intentionally an unpolished placeholder — the priority for this project is the targeting/firing Blueprint logic, not the mesh.
