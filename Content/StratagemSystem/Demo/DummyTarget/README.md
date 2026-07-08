# Demo / Dummy Target

A simple damageable actor used to playtest offensive Stratagems (Air Strike, Sentry fire) without needing real enemy AI.

| Asset | Purpose |
|---|---|
| `BP_DummyTarget` | The Actor placed in the level. Implements `BPI_Damageable` (see [`Blueprints/Interfaces`](../../Blueprints/Interfaces/README.md)) so any ability that deals damage can affect it without knowing it's a dummy |
| `SK_DummyTarget` / `SKM_DummyTarget` | Skeletal mesh and skeleton |
| `MM_Dummy_Colors` | Material function driving the color variants below |
| `MI_Dummy_DarkBrown`, `MI_Dummy_LightBrown`, `MI_Dummy_Rope` | Material instances — different color variants for visually distinguishing multiple targets in the test arena |
| `DummyTarget` | Source mesh asset |

> **This is test scaffolding, not a system component.** `BPI_Damageable` is the only thing this folder shares with the actual Stratagem System — everything else is disposable and specific to this demo.
