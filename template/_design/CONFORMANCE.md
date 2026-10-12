# CONFORMANCE — the drift detector

> Run with: "check conformance". This file lists what must agree with the design; an agent
> walks it, comparing each implementation file against the design source it names, and reports.

A design and an implementation drift apart one small honest decision at a time — a path that
moved, a rule that was never quite true, a document nobody re-read. This is the check that
catches it while it is still a discrepancy instead of the way things are.

## How it runs

1. For each item: read the implementation file and the design source it names.
2. Compare. Does the implementation match the design?
3. Mark it, and write a note on every failure — what differs, and which side is wrong.
4. Summary: *X of Y checks pass*.
5. The human decides: fix the implementation, change the design (with approval), or record an
   exception.

Automate what a machine can prove — files that exist, paths that resolve, mirrors that match.
Leave the judgement to the walk-through.

## The checklist

Keep the shape of each line: *what to look at* → *what it must match*.

### The entry chain

- [ ] `AGENTS.md` — the chain matches `_design/ARCHITECTURE.md`
- [ ] `MAP.md` — the domains match the domain map in `_design/ARCHITECTURE.md`
- [ ] `SCHEMA.md` — the frontmatter matches `_design/CONVENTIONS.md`

### The design

- [ ] `_design/CHARTER.md` — every principle still describes how the system works
- [ ] `_design/ARCHITECTURE.md` — the layers and paths match the folders on disk
- [ ] `_design/APPS.md` — the registry matches the actual app folders
- [ ] `_design/SKILLS.md` — the registry matches the skills that exist
- [ ] `_design/ABOUT-ME.md` — still short, still true, nothing added that was not asked for
- [ ] `_system-design/gap-analysis.md` — no closed gap still listed as open

### Stale paths

- [ ] No document references a folder that no longer exists
- [ ] No document references a tool that was replaced
- [ ] [the paths that have moved at least once — keep them here, so they cannot come back]

### Nothing that should not be here

- [ ] No credentials, keys or passwords in any file
- [ ] Nothing in the knowledge layer that belongs in the data layer
- [ ] [your own prohibition]

## The one rule

**If design and implementation disagree, the design is authoritative.** Either change the
design, with a human's approval, or fix the implementation. Never let them drift silently —
and never edit the design to match a mistake.
