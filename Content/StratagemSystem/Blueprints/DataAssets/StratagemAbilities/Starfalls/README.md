# Stratagem Abilities / Starfalls

Heavier, slower-resolving Stratagems — meant for a longer `DelayDuration` between signal and impact (the "something is falling from orbit" category), as opposed to the fast, sharp resolution of the `Ravens/` family.

## `PDA_Stratagem_Starfall`

The typed Data Asset subtype for this family. Extends `PDA_Stratagem_BASE` with fields specific to large-scale falling/impact effects (e.g. impact force, affected radius).

## Instances

*No instances configured yet.* This family currently only defines the type — no concrete Data Asset instance or ability Blueprint has been built on top of it.

> **Next step for this family:** create a `BP_StratagemAbilityBASE` subclass under [`Actors/Abilities`](../../../Actors/Abilities/README.md) implementing the staged signal → delay → impact behavior, then create a `PDA_Stratagem_Starfall` instance pointing to it.
