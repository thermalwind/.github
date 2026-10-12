# MAP — where things live

| Where | What it holds | Written by |
| --- | --- | --- |
| `Source/` | the originals: received documents, exports, contracts, e-mails; human-authored originals | a human, seldom |
| `knowledge/` | compiled pages — distilled prose, regeneratable | the agent, and a human |
| *no folder* — a store you choose | **structured data** with a shape: contacts, tasks, ledgers — held where the shape is enforced, not as pages | the agent within a workflow, and a human |
| `_design/` | the rules | a human, by approval |

## Your domains

[Replace with the domains this business actually has — sales, projects, finance, plant,
people, … — and which of the places above each one uses. Start with one domain and one
real document. A domain map with eight empty domains is a design, not a system.]

- `[domain]` — [what belongs here, and where it lives]

## The routing rule

Given a thing, ask in order; the first *yes* decides:

1. **Is it an original?** → `Source/`
2. **Is there a structured place designed for it?** → structured data, in a store that
   enforces the shape
3. **Neither?** → it stays knowledge. This is the default.

**A layer is a nature, not a folder.** Structured data has no folder in this vault: it has a
store — a database, a register, a task manager — because a record lives where the shape is
enforced, not in a page that merely shows it. A table pasted into a note is a note, not data.
That is why the table above gives a folder only to the layers that *are* places: the originals,
the compiled pages, and the design.
