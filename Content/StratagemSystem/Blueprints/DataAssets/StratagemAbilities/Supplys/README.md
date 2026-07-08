# Stratagem Abilities / Supplys

Utility/resupply-type Stratagems — no direct offensive or defensive effect, meant to hand the player resources (ammo, items) rather than damage or block enemies.

## `PDA_Stratagem_Supplys`

The typed Data Asset subtype for this family. Extends `PDA_Stratagem_BASE` with fields specific to resupply drops (e.g. item pool, drop height).

## Instances

*No instances configured yet.* This family currently only defines the type — no concrete Data Asset instance or ability Blueprint has been built on top of it.

> **Next step for this family:** create a `BP_StratagemAbilityBASE` subclass under [`Actors/Abilities`](../../../Actors/Abilities/README.md) that spawns a lootable crate or resource pickup, then create a `PDA_Stratagem_Supplys` instance pointing to it.
