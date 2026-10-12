# Gap analysis — the target vs today

**The blueprint is the target. `_design/` is the truth of today.** This page holds the
distance between them — and the distance runs in **two directions**:

- **Shortfalls** — where the running system is narrower than the blueprint.
- **Advances** — where the implementation is ahead of the blueprint, and the blueprint should
  absorb what was learned in practice.

## 1 · Shortfalls

| # | Dimension | The ideal | Today | Gap to close | Class |
| --- | --- | --- | --- | --- | --- |
| G1 | [users & trust] | [what the blueprint says] | [what `_design/` does] | [the work] | 🔴 |
| G2 | [onboarding] | | | | 🟡 |
| G3 | [design vs instance] | | | | 🟡 |

**Class** — 🔴 blocks handing the system to someone else · 🟡 can be closed later · 🟢 a
decision to write down, not work to do.

## 2 · Advances

| # | Innovation | Where it lives today | Why the blueprint needs it |
| --- | --- | --- | --- |
| A1 | [what we invented in practice] | [`_design/…`] | [what the ideal is missing] |

The second table is the one people forget. An analysis that only lists what is missing turns
the blueprint into a stick to beat the implementation with; the advances are the reason to
write the blueprint at all.

## 3 · The shortest path

Ranked by what unblocks the next step soonest — not by size, and not by tidiness.

1. [the gap that unblocks the most]
2. …
3. …

## 4 · What this changes in `_design/`

For approval — not yet done:

| # | Document | Change |
| --- | --- | --- |
| 1 | [`_design/CONFORMANCE.md`] | [what to add or correct] |

## The rule

`_design/` is read-only for an agent. Nothing on this page changes it; each line names a change
that needs a human's approval. Where this page and `_design/` disagree on *today's behaviour*,
`_design/` wins.
