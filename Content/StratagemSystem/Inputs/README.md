# Inputs

Enhanced Input configuration for the system, built on UE5's native Enhanced Input plugin.

## Mapping Contexts

| Context | Purpose |
|---|---|
| `IMC_DefaultGameplay` | Base gameplay bindings — movement, look, jump |
| `IMC_StratagemControls` | Directional + activation bindings for entering a Stratagem sequence |

`IMC_StratagemControls` is added with a **higher priority** than `IMC_DefaultGameplay` while the Stratagem menu is open, so directional inputs go to the sequence system instead of movement. It's removed again when the menu closes, returning control to normal gameplay bindings.

## `Actions/`

See [`Actions/README.md`](Actions/README.md) for the individual Input Actions.

> **Integrating into your own project:** you only strictly need `IA_ActivateStratagem` and `IA_DirectionalInputs`, plus a Mapping Context that raises their priority over your own movement inputs while the Stratagem menu is active. `IA_Jump`, `IA_Look`, and `IA_Move` belong to the demo's character controller, not the system itself.
