# Blueprint — the target

> **Status**: [adopted · in progress · rewritten]. This is *your* target, not one you
> inherited.

Write your blueprint here. The starting point is the published one:

**[The published blueprint](https://github.com/thermalwind/.github/blob/main/blueprint.md)** —
read it, then write your own version in this file: cut what does not apply to your business,
rewrite what does, add what it is missing.

It is deliberately **not** copied in here. A file that exists twice is a claim that will drift,
and the link above keeps working after you move this folder into your own vault — which a
relative link would not. Use the [raw
text](https://raw.githubusercontent.com/thermalwind/.github/main/blueprint.md) if you want to
paste it in and edit from there.

A blueprint you have not edited is a proposal someone handed you; a blueprint you have edited
is a design you can defend.

## What a blueprint must answer

If a section cannot be answered for *your* business, it is not finished. The published
blueprint is a worked example of this list:

1. **The idea in one line** — what the system is, without naming a tool.
2. **The problems observed** — what is actually broken today. Concrete, dated, yours.
3. **The principles** — the handful that will not change when the tools do.
4. **The layers** — what the system is made of, and which parts are authoritative.
5. **Two natures** — what is compiled knowledge and what is structured data, and why they
   behave differently.
6. **The routing rule** — given a thing, where does it go?
7. **The lifecycle** — how material is taken in, worked on, and fed back.
8. **The agent model** — what the agent may do alone, and what needs a human.
9. **Structured data** — what is kept as records, and in what.
10. **Trust & governance** — who may see and change what, and how you prove it.
11. **What implements this today** — the honest state, with the gaps named.
12. **Terms** — the vocabulary, so two people mean the same thing.

## The rules for writing one

- **Declarative, present tense.** "Source is read-only." Not "we should consider making Source
  read-only."
- **No local specifics.** Tools, paths, hostnames and product names belong in `_design/`. The
  moment a blueprint names a tool, it ages with that tool.
- **No mechanism.** The blueprint says *what is true*; `_design/` says *how it is done*.
- **Say the gap out loud.** A blueprint that describes a system you do not have is a wish. Put
  the distance in `gap-analysis.md`.
