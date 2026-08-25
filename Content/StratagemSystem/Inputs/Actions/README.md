# Inputs / Actions

| Input Action | Bound to | Belongs to |
|---|---|---|
| `IA_OpenStratagem` | Hold to open the Stratagem menu / start listening for a sequence | **System** |
| `IA_ActivateStratagem` | Confirm / throw once a sequence is complete | **System** |
| `IA_DirectionalInputs` | The four directions (Up/Down/Left/Right) fed into `BPC_StratagemSystem`'s sequence validator | **System** |
| `IA_Move` | Character movement | Demo character |
| `IA_Look` | Camera look | Demo character |
| `IA_Jump` | Character jump | Demo character |

The three marked **System** are the only ones the Stratagem System itself depends on. The rest exist for the demo's playable character and aren't required to use the system in another project.
