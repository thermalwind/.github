# SKILLS — the registry

> Every capability the system has, in one list, with where it lives and what it is for.

A skill is a **declared workflow** an agent follows and can adapt — unlike a script, which
does one deterministic job and judges nothing. Both are programs; the difference is who
decides. Put the judgement in the skill, the mechanics in a script.

## The registry

| Skill | Path | What it does | Trigger |
| --- | --- | --- | --- |
| [example-skill] | [`.agents/skills/example-skill/`] | [the outcome it produces] | [the words that should summon it] |
| … | | | |

The **trigger** column is not decoration. It is the same sentence that lives in the skill's
`description`, and it is the only thing an agent reads before deciding whether to open the
skill. A skill with a vague trigger is a skill that never runs.

## Worked examples

Ten skills from a running system of this shape. Read the last column: that is what each one is
there to show about what a skill *is*.

| Skill | What it does | Trigger | What it shows |
| --- | --- | --- | --- |
| `wiki-ingest` | takes any source — a PDF, a folder, a chat export, a URL — and distils it into interlinked pages | "add this to the wiki", "process these docs" | a **pipeline**: several modes, one output shape, and it works from a declared source list instead of deciding for itself |
| `mail` | search, read, reply, compose and send — where composed mail lands as a reviewable draft first | "check my inbox", "reply to Z" | a skill that **wraps an outside system**, and keeps the dangerous verb — send — behind a review |
| `slides` | build, restyle, present and export a deck | "make a presentation", "turn this into slides" | a skill with **references and scripts beside it** — the playbook is too big for one file and is still one capability |
| `publish` | builds a public export, strips the private material, runs a gate, opens a pull request | "publish this", "put it on our git page" | a skill with a **hard gate** — it fails instead of guessing, and carries an explicit *never* list |
| `register` | reads and writes a live project register — schema, rows, views | "the register", "run the export" | a skill over **structured data**, where every write goes through a committed action file first |
| `task-create` | turns a one-line request into a properly-formed task file | "create task", "add a task for X" | a skill that **enforces a format** — and confirms its own inference before it writes |
| `audit` | audits the knowledge base and reports; with a flag it also fixes, and reports | "clean up the wiki", "what needs fixing" | a **report-first** skill: acting is a flag, and it previews before it writes |
| `preflight` | checks at session start that the design and the implementation still agree | "check conformance", "is this consistent" | a skill that **never edits anything** — it exists to make drift visible, not to repair it |
| `daily-update` | runs the maintenance cycle and refreshes the index | "/daily-update", or a scheduled run | a skill driven by a **schedule** as well as a sentence — same workflow, same entry point |
| `pick` | builds a small, diverse watchlist from the knowledge base's own interests | "make my watchlist", "what should I watch" | a skill with its **anti-goal written down** — it never seeds from the platform's own history |

Four patterns worth copying straight out of that list:

- **A skill that cannot refuse is a liability.** `publish` fails rather than guess; `preflight`
  never edits; `pick` carries a prohibition. A skill with no *never* has no judgement in it.
- **The format is the product.** `task-create` and `audit` are worth as much for the shape of
  what they produce as for the work they do — that shape is what makes the output readable by
  the next thing.
- **Write paths stay narrow, read paths stay wide.** `register` reads everything and writes
  through one committed file; `mail` reads freely and sends only what a human has seen.
- **One skill, several files.** `slides` and `publish` are one capability each, with references,
  templates or scripts beside them. Splitting them into four skills would not make them simpler.

## The skill-first rule

Before doing a multi-step job by hand, look for a skill that already does it. If one exists,
use it. If none exists and the job will recur, write one — a workflow an agent repeats from
memory is a workflow that is done differently every time.

This is a rule about *where the knowledge lives*. A procedure that only exists in a
conversation is not a capability; it is a coincidence.

## What a skill must carry

- A **description that names its triggers**, in the words a person would actually use. Say the
  phrases out loud in the description — "when the user says X, Y or Z" — because that is what
  the agent matches against.
- **Steps** that say what to read first, what does the work, and where the output goes —
  which layer, which folder, which frontmatter.
- **Rules** that say what must never happen, and to stop and ask when the input is missing
  rather than invent one.

## Registry discipline

- One skill, one job. A skill that does two things gets summoned for the wrong one.
- A skill that is superseded is **deleted**, not kept as a second way to do the same thing.
- A skill that touches Source reads it and never writes back.
- A skill that is never triggered is either badly described or unnecessary — check the
  description before writing a new one that overlaps it.
- If the skill changes, this registry changes in the same pass.
