# CONVENTIONS — naming, frontmatter, citation

## Names

- `lowercase-with-hyphens` for pages and folders. No dates in a title, no version numbers —
  the frontmatter carries those.
- Folders are **domains**, not types: `sales/`, not `reports/`. A folder named after a
  document type collects everything and organises nothing.
- One concept, one page. Two pages for the same thing is how a knowledge base starts lying.

## Frontmatter

Every page carries the fields in `SCHEMA.md`. `summary` is one line, and it is what an index
reads. A page without a summary is invisible to every index you will ever build.

## Citation

A claim that came from a document carries its pointer and its mark:

- **extracted** — stated in the source
- **inferred** — concluded from it
- **ambiguous** — the source can be read more than one way

A claim without a pointer is not usable. If you cannot say where it came from, say that
instead of stating it.

## Writing

- State facts. Do not narrate the process that produced them.
- Dates absolute (`2026-10-12`), never "yesterday" or "last week".
- Say "unknown" when it is unknown. A gap is information; a guess is a liability.
- [The company's own voice rules — what a document here sounds like.]
