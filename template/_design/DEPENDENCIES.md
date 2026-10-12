# DEPENDENCIES — the inventory

> **Status**: [started · living]. An empty page is fine; a page that lies is not.

## 1. Purpose

One question: **is this something I take, or something I wrote?**

Everything on this page is something you *take* — a program, a service, a package, a plugin. What
you write yourself — the skills, the design — is not a dependency; it is the system. Keeping those
two apart is what stops a design from turning into a list of tools, and it is what makes every tool
below replaceable without rewriting the design.

The page exists so that no fact has two homes. When a document needs to know *why* a tool is there,
it links here instead of restating it.

## 2. The rule

- **Every document links its dependencies here.** `DEPENDENCIES.md` is the single inventory: a
  module states *what it uses*, this page states *what that is, why, and where it comes from*.
- **A dependency named nowhere is undocumented.** A module that leans on something unlisted has an
  unrecorded dependency.
- **One entry per dependency**, always the same four fields.
- **Updated in the same pass as the change** — added, upgraded, dropped. The drift is then visible
  in review, which is the only reason the page is worth keeping.

## 3. At a glance

| Layer | Depends on |
| --- | --- |
| The method | the pattern · the skills · the design layer — nothing to install |
| Platform & runtime | [ ] |
| Registers & project data | [ ] |
| Documents | [ ] |
| Web search | [ ] |
| Mail · calendar · contacts | [ ] |
| Libraries | [ ] |
| Obsidian plugins | [ ] |
| Desktop applications | [ ] |

Add a layer when a real dependency does not fit an existing one — not before.

## 4. The entry shape

### [name]

| | |
| --- | --- |
| **What** | one line: what it is, and what it is not |
| **Why** | what it buys you — the load-bearing field |
| **Used by** | the skills, scripts and pages that lean on it |
| **Source** | where it comes from, and how you get it back |

Three rules for the fields.

**The Why is the load-bearing one.** A dependency whose Why is unclear is one you will keep for
the wrong reason, long after the reason has gone.

**Source is a way back, not a citation.** If the vendor disappears, the URL should be enough to
rebuild or replace it. A package you install by name is a source; "it came with the machine" is
not.

**One entry, one dependency.** "The mail stack" is a layer, not an entry — each program inside it
gets its own line, with its own Why.

## 5. What never goes on this page

This page is the one most likely to be copied, handed over, or published. So:

- **No addresses.** No IP numbers, no hostnames, no ports, no machine names. If you self-host
  something, the entry says *that* you do and what for — the topology lives in your own notes, on
  your own machine.
- **No secrets.** No keys, tokens or passwords — not even one that is "only for the local network".
- **No personal or client data.** Not in the entry, not in the Why, not inside a path.
- **No private counts.** How many machines, clients or records you have: none of it belongs here.

A hand-over is a filtered copy, not a folder paste: `visibility: internal` pages never leave.

## 6. Worked examples

Five dependencies from a running instance of this shape. Read the last column: that is what each
one is here to show.

| Dependency | What it is | Why it is here | What it shows |
| --- | --- | --- | --- |
| `git` | version control for the vault and every script tree | history, review, and the rollback when the agent gets something wrong | a dependency that is also a **safety net** — the one you miss most |
| `Obsidian` | the editor and the host: files, links, Bases, plugins, the agent | the front end of the whole system | a dependency you **live inside** — so the file format matters more than the app |
| `SearXNG` | a self-hosted meta-search engine | grounding outside the vault, with no vendor and no key | a dependency **you run yourself**, and the one whose entry most needs the no-addresses rule |
| `obsidian-wiki` | a packaged skill framework that implements the compiled-wiki pattern | the whole skill set at once, instead of deriving it from an essay | a dependency you are **allowed to edit** — take it, then change it |
| `MCP Python SDK` | the client and server library for the tool-calling standard | how a script becomes a tool the agent can call | a **library**: small, boring, and the reason the programs above it stay replaceable |

## 7. Related

- `_design/APPS.md` — the workspaces *you* build, as opposed to the programs you take
- `_design/SKILLS.md` — the capabilities *you* declare, and their triggers
- `_design/CONFORMANCE.md` — the check that this page and the running machine still agree
- `.agents/skills/example-skill/SKILL.md` — what a capability looks like next to the tools it drives
