# ARCHITECTURE — the layers, and who may write

Two authorities stand **outside the loop** — **Design** (the rules) and **Source** (the
truth) — reachable only through an approval **gate**. Inside the loop sit the three things
the agent works with: **knowledge** (it reads), **data** (it works) and **programs** (it
runs). The **agent** is not a layer; it moves between them.

| Layer | Holds | Written by | Regeneratable |
| --- | --- | --- | --- |
| **Design** | these files: charter, architecture, conventions | a human, by approval | no — it is the design |
| **Source** | the originals | a human, seldom | no |
| **Knowledge** | compiled pages | the agent **and** a human | yes — the generated text |
| **Data** | records with a shape | the agent in a workflow, and a human | no |
| **Programs** | skills, scripts, the chain | a human; the agent through the gate | no |

## The routing rule

Given a thing, ask in order; the first *yes* decides:

1. **Is it an original?** → `Source/`
2. **Is there a structured place designed for it?** → a record, in a store that enforces
   the shape
3. **Neither?** → it stays knowledge. This is the default.

## The two rules that keep it honest

- **One-way wall.** Source and Design are reached only through a gate. Everything else the
  agent may draft freely.
- **Cite, never copy.** Where an authority backs a thing, that thing carries a pointer back
  and never a duplicate: a compiled page cites its original, a record keeps its provenance,
  a skill registers into the index. A copy is a claim that will drift.

## What to write here next

[The concrete tools and paths for this company — which editor, which store, where the
originals land. Name them: this file is about the *how*, and the blueprint is not.]
