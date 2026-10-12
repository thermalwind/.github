# SCHEMA — what a page looks like

Every page carries the same frontmatter. Nothing here is optional, and nothing else is
required: a schema that grows a field per document is not a schema.

```yaml
---
title:
type:        # note · record · design · source · report
domain:      # one of your domains (see MAP.md)
origin:      # authored · extracted · inferred · generated
lifecycle:   # draft · adopted · superseded
visibility:  # internal · client · public
created:
updated:
summary:     # one line — what an index reads instead of the body
---
```

## How the fields are used

- **`origin`** records where the claim came from, not who typed it. `generated` means the
  agent wrote it and it can be rebuilt; `authored` means a person stands behind it.
- **`lifecycle`** — `draft` may be rebuilt by the agent; `adopted` is frozen and rebuilds
  work around it; `superseded` points at what replaced it.
- **`visibility`** gates a hand-over. An export is filtered by this label, one page at a
  time — never a folder copied wholesale.
- **`summary`** is one line. It is what makes an index possible without reading every body.

## The rule behind the fields

A page that cannot say where it came from is not usable in a decision. That is the whole
reason the frontmatter exists — it is not bookkeeping for its own sake.
