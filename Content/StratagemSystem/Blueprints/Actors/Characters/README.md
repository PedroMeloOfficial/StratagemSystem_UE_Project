# Actors / Characters

The Character Blueprints used to **demonstrate** the Stratagem System. These are not part of the reusable system — they exist so `BPC_StratagemSystem` has something to attach to and be tested on.

| Blueprint | Purpose |
|---|---|
| `BP_CharacterBase` | Base movement/input character shared by the demo |
| `BP_Player` | The playable character — hosts `BPC_StratagemSystem` and implements `BPI_GetPlayerController` / `BPI_GetHudWidget` so the component and HUD can talk to it |

## `Anims/`

| Asset | Purpose |
|---|---|
| `ABP_FP_Copy` | First-person Animation Blueprint for the demo character |
| `CtrlRig_FPWarp` | Control Rig used for first-person hand/arm IK warping (weapon aiming, sway) |

> **If you're integrating the system into your own project:** you don't need any of this folder. Add `BPC_StratagemSystem` to your own Character class, implement the two interfaces above, and you're done. This folder is reference/demo material only.
