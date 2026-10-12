# `_system-design/` — the target

Two folders, two different things — and mixing them is the most common way a design stops
being useful:

- **`_design/`** — how the system runs **today**: the tools, the paths, the rules as they are.
- **`_system-design/`** — how it **should** run: the ideal, written down before it exists.

This folder holds the ideal and the distance to it. Read it when you are deciding what to
build next; ignore it when you are doing today's work.

## What lives here

| File | What it is |
| --- | --- |
| `blueprint.md` | the target — your design from first principles. Starts as a pointer to the published one; becomes your own text |
| `gap-analysis.md` | the distance between the target and `_design/`, in both directions |

## The rule that keeps this folder honest

`_design/` is the truth of today. Where the two disagree on *current behaviour*, `_design/`
wins — and the disagreement is a **gap**, not a licence to describe the system as you wish it
were. An agent may not edit `_design/` to make a gap disappear. The gap gets closed, or it
gets written down as accepted.
