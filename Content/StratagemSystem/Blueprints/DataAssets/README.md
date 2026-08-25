# Data Assets

This is where the "data-driven" half of the architecture lives. Every value that can change per-Stratagem, per-type, or per-input lives here, not in a Blueprint graph.

## Three separate concerns, three separate hierarchies

It's easy to assume "Stratagem data" is one thing. It isn't — this system separates three questions that don't change together:

| Folder | Question it answers | Changes how often? |
|---|---|---|
| [`StratagemAbilities/`](StratagemAbilities/README.md) | *What does this specific Stratagem do, and how is it configured?* | Every time you add a new Stratagem |
| [`StratagemTypes/`](StratagemTypes/README.md) | *What category is this Stratagem, and what color represents it in the UI?* | Rarely — only when adding a whole new category |
| [`StratagemInputs/`](StratagemInputs/README.md) | *What does "Up" mean as a data object, not a hardcoded key?* | Almost never |

Keeping these separate is what lets you, for example, add a brand-new Stratagem family without touching `StratagemTypes` at all, or reskin every Stratagem's color coding without touching a single ability.

> **If you're not sure where a new variable belongs:** ask whether it's true of *one ability*, *a whole category of abilities*, or *the input system itself*. That answers which folder it goes in.
