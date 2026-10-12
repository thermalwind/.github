# The template `_design`

The smallest version of the design that still works: the files a business fills in for itself,
stripped of everything that belongs to one particular company.

[The blueprint](../blueprint.md) says how the system is shaped. This is the shape. Copy the
folder to the root of your own vault, then replace every `[placeholder]` with your own words.
Nothing here is a blind copy of someone else's setup — a design you did not write is a design
you cannot change.

## The two folders

The design has two halves, and keeping them apart is what stops it going stale:

- **`_design/`** — how the system runs **today**. Concrete: the tools, the paths, the rules.
- **`_system-design/`** — how it **should** run, and the distance to today. No local specifics.

## What each file is for

| File | The question it answers |
| --- | --- |
| `AGENTS.md` | what an agent reads first, and which rules it must not break |
| `MAP.md` | where things live — which domain holds what |
| `SCHEMA.md` | what a page looks like: the frontmatter every page carries |
| `_design/CHARTER.md` | why the system exists, for this company |
| `_design/ARCHITECTURE.md` | the layers, and who may write to each |
| `_design/CONVENTIONS.md` | naming, frontmatter, citation |
| `_design/SKILLS.md` | the registry: every capability, where it lives, when it triggers |
| `_design/DEPENDENCIES.md` | every program you take, why it is there, and the rule that addresses never enter it |
| `_design/APPS.md` | what counts as an app — and every app's change log |
| `_design/CONFORMANCE.md` | the drift detector: design against implementation |
| `_design/ABOUT-ME.md` | how this person wants to be worked with |
| `_system-design/blueprint.md` | the target — your design. Points at the [published blueprint](https://github.com/thermalwind/.github/blob/main/blueprint.md), then becomes your own text |
| `_system-design/gap-analysis.md` | the distance between the target and today |
| `.agents/skills/example-skill/SKILL.md` | what a capability looks like — the shape to copy |
| `Source/` | the originals: received or human-authored, never modified by a tool |
| `knowledge/` | the compiled layer: distilled pages, regeneratable |

## The order to fill it in

1. `_design/CHARTER.md` — in your own words. Everything else follows from why.
2. `_design/ABOUT-ME.md` — how you want to be worked with. Half of the system's behaviour is
   settled here, and it is the cheapest file to write.
3. `MAP.md` — your domains. Start with one.
4. `SCHEMA.md` — keep the fields, change the values.
5. A skill of your own. Copy `example-skill`, rename it, describe your own workflow — or take a
   ready-made set instead of writing each one; [Implement it](../implement.md) names the routes.
6. `_design/DEPENDENCIES.md` — open it now and keep it open. Every program you install gets a
   line, and the *why* is the part that saves you later. It fills itself in as you work.
7. `_system-design/blueprint.md` — later, and deliberately last. Write it once the system has
   answered a real question, so the blueprint describes something you have actually seen
   rather than something you hope for.

Read the blueprint for the reasoning behind each layer. Do not copy a design you do not
understand — the first time reality disagrees with it, you need to know what you meant.
