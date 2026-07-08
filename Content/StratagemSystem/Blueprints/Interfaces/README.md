# Interfaces

Blueprint Interfaces exist to keep `BPC_StratagemSystem` and the HUD decoupled from any specific Character class. Instead of casting to `BP_Player`, the system calls an interface function — meaning the component works on *any* Pawn that implements it.

| Interface | Implemented by | Used to |
|---|---|---|
| `BPI_GetPlayerController` | `BP_Player` | Let `BPC_StratagemSystem` reach the owning PlayerController without a hard cast |
| `BPI_GetHudWidget` | `BP_Player` | Let the component find and update the active HUD widget |
| `BPI_GetPDAStratagem` | `BP_StratagemAbilityBASE` subclasses | Let external systems (HUD, cooldown display) query which Data Asset backs a given ability instance, without knowing its concrete class |
| `BPI_Damageable` | Anything that can take damage (e.g. `BP_DummyTarget`) | Let ability effects (AirStrike, Sentry fire) apply damage without needing to know the target's class |

> **Why interfaces instead of a common base class here:** the things implementing these interfaces don't otherwise share behavior — a dummy target and a real enemy character have nothing in common except "can take damage." An interface expresses exactly that shared contract without forcing an inheritance relationship that doesn't otherwise make sense.

> **Integrating this system into your own project?** Implement `BPI_GetPlayerController` and `BPI_GetHudWidget` on your own Character class instead of using `BP_Player` — that's the extent of what the component needs from you.
