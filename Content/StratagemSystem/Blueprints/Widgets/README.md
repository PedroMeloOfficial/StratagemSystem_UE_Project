# Widgets

The HUD — everything the player sees while entering a Stratagem sequence and while abilities are on cooldown.

| Widget | Role |
|---|---|
| `BP_HUD_StratagemSystem` | Root HUD widget. Binds to `BPC_StratagemSystem`'s event dispatchers and drives everything below it |
| `WB_Hud` | General HUD container |
| `WB_HorizontalBox` | Layout widget arranging the available Stratagems / input feedback in a row |
| `WB_ArrowBox` | Displays a single Stratagem's input sequence as a row of directional arrows, updating each arrow's state (pending → accepted) as the player inputs it correctly |

## How this connects to the system

`BP_HUD_StratagemSystem` never reaches into a specific Character. It gets its data through:
- `BPC_StratagemSystem`'s event dispatchers (see [`Components/`](../Components/README.md)) for input/cooldown/deployment state
- `BPI_GetPDAStratagem` (see [`Interfaces/`](../Interfaces/README.md)) to pull display data (icon, name, `TypeColor`) straight from the relevant Data Asset

This means the HUD never hardcodes a Stratagem's name, icon, or color — all of it comes from the Data Asset chain described in [`DataAssets/`](../DataAssets/README.md). Add a new Stratagem, and the HUD displays it correctly with zero widget changes.
