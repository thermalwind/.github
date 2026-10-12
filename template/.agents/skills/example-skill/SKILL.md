---
name: example-skill
description: [What it does, and when to use it — in the words a person would actually say. Write the trigger phrases out: "when the user says X, Y or Z". This field is the only thing an agent sees before it decides whether to open this skill, so a vague description means the skill never runs.]
---

# [The skill]

[One paragraph: the outcome this skill produces, and what it needs to start — an input
file, a source document, a decision from a human.]

## Steps

1. [What to read first, and why.]
2. [The step that does the work.]
3. [What to produce, and where it goes: which layer, which folder, which frontmatter.]

## Rules

- [What must never happen here — the thing that would make this skill a liability.]
- [What to do when the input is missing or ambiguous: stop and ask, never invent.]

## Why this shape

A skill is a **declared workflow** the agent follows and can adapt — unlike a script, which
does one deterministic job and judges nothing. Both are programs; the difference is who
decides. Put the judgement in the skill, the mechanics in a script.
