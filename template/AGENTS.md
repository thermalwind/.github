# AGENTS.md — how an agent works in this vault

> Read this first. Then follow the chain.

## The chain

1. `MAP.md` — where things live
2. `SCHEMA.md` — what a page looks like
3. `_design/` — the rules: CHARTER, ARCHITECTURE, CONVENTIONS, SKILLS, APPS, CONFORMANCE
4. `.agents/skills/` — the capabilities. If a skill exists, never do its job by hand.
5. `_system-design/` — the target and the gap. Read it when deciding what to build next, not
   when doing today's work.

## The rules

- **The originals are read-only.** Nothing in `Source/` is modified by a tool.
- **The design is binding**, and changing it needs a human approval — a gate.
- **What the agent writes is a draft.** The generated text is a cache: delete it, rebuild it.
  The asset is the originals, the human's own edits and the design.
- **Source and Design change only when a named human approves.**
- **A human edit ends the agent's ownership** of that page — take the edit as an instruction.
- **Every page is either draft or approved**, and generated text is marked `generated`.
- **Cite, never copy.** A claim from a document carries the pointer back to it.
- **Design and implementation move together.** When you change how the system works, update the
  design in the same pass — and when you are asked to check, walk `_design/CONFORMANCE.md`.
- Name a tool where that makes the design clearer. Keep the design itself tool-agnostic.

## What is not here

No roles, no personas, no memory an agent keeps between sessions. One session is the model,
its tools, this chain and the skills — what it knows, it reads from the layers.
