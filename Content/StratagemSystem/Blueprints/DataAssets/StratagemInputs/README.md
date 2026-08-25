# Data Assets / Stratagem Inputs

Represents a directional input as a data object instead of a hardcoded enum value or key reference. This is what a Stratagem's `InputSequence` array is actually made of.

## `PDA_StratagemInput`

The base Data Asset. Minimal by design — just enough to identify a direction and (optionally) how it should be represented in the HUD's input feedback widget.

## Instances

| Data Asset | Direction |
|---|---|
| `DA_Up` | Up |
| `DA_Down` | Down |
| `DA_Left` | Left |
| `DA_Right` | Right |

These four are referenced, in whatever order, by every `PDA_Stratagem_BASE` instance's `InputSequence` field to define its unlock combination.

> **This folder almost never needs to change.** Four directions cover every sequence in the system. If the input scheme ever expands (e.g. diagonal inputs, a 5th button), that's the only reason to add a new instance here.
