# APPS — application workspaces

> **Status**: [implemented · partial]. This document defines the concept, the registry and the
> rules.

## 1. Purpose

An **app** is a self-contained workspace that a tool or a workflow operates on: its scripts,
config, templates and generated output, all in one folder. The layer exists so those do not
end up scattered through the managed layer, mixed in with the flat data they operate on.

It answers one question: **is this a self-contained thing a tool operates on, or is it flat
data edited in place?** The former is an app; the latter stays where it is.

## 2. What counts as an app

A folder is an app when it:

1. represents a **tool or a domain** with its own working files, scripts or output;
2. is **self-contained** — its files belong together and are not spread through the vault;
3. is **maintained by an agent or a script** inside a defined workflow;
4. usually has a **dedicated skill** or script that drives it.

**Not apps:** shared tooling used by several apps · the data an app operates on · a subset of
the vault synced somewhere else · the **programs an app is built on** — those are dependencies
(`DEPENDENCIES.md`), and they outlive the app.

## 3. Worked examples

Ten apps from a running system of this shape, one per kind. The point is the **range** — an
apps layer that only holds bookkeeping-style apps has not been understood yet. Read the last
column: that is what each one is there to show.

| App | What it is | Driver | What it shows |
| --- | --- | --- | --- |
| `bookkeeping` | the books for a sole trader and a holding: bank import → ledger → statements | skill + a reporting tool | a **domain app** — one skill, several sources, output that is explicitly never the record |
| `content-creator` | drafts for social posts, articles and proposals, with a state per piece | skills | an app with **workflow states** — outline → draft → review → published, and a folder per channel |
| `mail` | live mailboxes: search, reply, compose, plus a one-way mirror for offline search | skill | an app whose data is **remote** — the app holds the interface, the provider holds the record |
| `calendar` | live calendars and contacts, plus a read-only merged feed for the view | skills | an app that **exports downward** — everything flows one way into a file the system can read |
| `register` | project data as linked tables — groups, items, offers, prices — instead of one note per row | skill + a database | the **app vs data** rule: the folder is the tool, the rows are the data, and they have different owners |
| `dashboard` | one screen: today's tasks, who to follow up with, the last 24 hours of mail | script | an app that **reads everything and owns nothing** — it is pure output |
| `home-automation` | a few hundred devices: lights, heating, solar, media | scripts | an app with **hardware** — verified live, and every change needs a way back |
| `mail-archive` | read-only search through an old zipped mailbox, with attachment extraction | skill | a **stateless** app — stores nothing, can be deleted without loss |
| `logbook` | a hobby logbook, digitised page by page | script | that apps are **not only business** — this is where that hobby's data lives |
| `photos` | a long-term photo archive: where it is, how things get in, how they are tagged | script | an app that documents a **workflow**, not a tool |

Two patterns worth copying straight out of that list:

- **The app owns the tool, never the record.** `register` holds the cost model; the rows it
  reads live in the database. Delete the app folder and you have lost convenience, not data.
- **The state matters more than the content.** `content-creator` is an app because each piece
  has a *state* and a *channel*; a folder of loose drafts is not an app, it is a pile.

## 4. Registry

| App | Path | Purpose | Driver | Design doc |
| --- | --- | --- | --- | --- |
| [`app-name`] | [`apps/app-name/`] | [what it is for] | [the skill or script] | [`_design/….md`] |
| … | | | | |

The human-readable entry point is `apps/index.md`.

## 5. Rules

- **Naming**: `lowercase-with-hyphens`.
- **Survival**: apps are managed data — they survive a rebuild and are never auto-deleted.
- **Source wall**: an app reads Source on demand and never writes back into it.
- **Skill-first**: if the app has a skill, use it instead of hand-rolling the workflow.
- **App vs data**: the folder holds the **tool**; the irreplaceable data it operates on lives
  in the data layer — never inside the app folder.
- **Self-contained**: reference an app from elsewhere by linking, never by copying its content.

## 6. The change log — every app keeps one

> The app's own record of *what an agent changed, why, and how to undo it*.

Git records *that* a line changed. It does not record why, whether it was verified, or how to
get back. The change log is that record, kept next to the app, so the next session starts
informed instead of re-deriving.

The app with hardware above is the reason this section exists: a change to a device that
cannot be undone, and nobody wrote down what was tried.

**The rule**

- Every app has one — a `## App Change log` section in its own `index.md`, never a separate
  file, so it stays with what it describes.
- **Append-only.** A mistake gets a *new* entry that corrects it; history is never rewritten.
- **Every entry can be reverted.** An entry without a *how to revert* is incomplete.
- **Owner is the changer**, in the same session.

**The format** — depth follows the app. Light, for small self-evident changes:

```markdown
## App Change log

- 2026-01-04 — first import; three sections created.
```

Heavy, for apps with state, hardware or irreversible steps:

```markdown
### 2026-01-04 — short title

Context: the request, verbatim where it matters.

| # | Change | Detail | How to revert |
| --- | --- | --- | --- |
| 1 | what changed | the concrete detail | the exact undo step |

**Verified:** what was checked live, and what was not.
**Open items:** what remains.
```

## 7. Adding an app

1. Create `apps/<app-name>/`.
2. Add an `index.md` describing purpose, structure and workflow — including a
   `## App Change log` section, even if empty at first.
3. Decide where its **data** lives, and keep any app↔data mapping inside the app folder.
4. Register it here and in `apps/index.md`.
5. Write the driving skill, and register it in `_design/SKILLS.md`.
