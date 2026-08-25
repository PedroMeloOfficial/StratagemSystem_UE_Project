# Components

## `BPC_StratagemSystem`

The single integration point for the entire system. Attach this Actor Component to any Character or Pawn and the Stratagem System becomes available on it — no other setup required.

This component owns:

- **Input state** — the sequence of directional inputs entered so far, and the timer that resets it if the player pauses too long.
- **The registered Stratagem list** — which `PDA_Stratagem_BASE` subtype assets are available to this instance.
- **Cooldowns** — one independent timer per registered Stratagem.
- **The deployment pipeline** — from a completed sequence, to throwing the beacon, to spawning the resolved `BP_StratagemAbilityBASE` subclass.

> **Composition, not inheritance.** Nothing about this component depends on `BP_Player` or `BP_CharacterBase`. Any Actor that owns one gets working Stratagems. This is what makes the system portable between projects.

## Events other systems can listen to

The HUD (see [`Widgets/`](../Widgets/README.md)) and any other system that cares about Stratagem state should bind to this component's event dispatchers rather than polling it every frame. Look for events covering:

- Menu opened / closed
- An input accepted or rejected
- A full sequence completed (which Stratagem was selected)
- A Stratagem deployed (and where)
- Cooldown started / ended

> **Don't Tick this.** Every piece of state changes in response to an event (input pressed, timer expired, sequence completed) — there's no reason for this component to run every frame. If you add a feature here, make it event-driven too.

## Talking to a specific Character without a hard reference

If `BPC_StratagemSystem` needs to ask its owner something (e.g. "where should the beacon spawn from"), it does so through [`BPI_GetPlayerController`](../Interfaces/README.md) rather than casting to `BP_Player` directly. This keeps the component usable on any Pawn, not just the demo's player character.
