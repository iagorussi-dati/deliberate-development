---
name: improve-codebase-architecture
description: Surface architectural friction and propose deepening opportunities — refactors that turn shallow modules into deep ones. Use when exploring architecture improvements, finding coupling issues, or wanting to deepen modules.
---

# Improve Codebase Architecture

Surface architectural friction and propose **deepening opportunities** — refactors that turn shallow modules into deep ones.

Uses the vocabulary in [LANGUAGE.md](LANGUAGE.md) — **module**, **interface**, **seam**, **adapter**, **leverage**, **locality**.

## Process

### 1. Explore

Read the project's domain glossary and any ADRs first. Then explore organically noting:
- Where does understanding one concept require bouncing between many small modules?
- Where are modules shallow — interface nearly as complex as the implementation?
- Where have pure functions been extracted just for testability, but the real bugs hide in how they're called?
- Where do tightly-coupled modules leak across their seams?

### 2. Present candidates

For each candidate show:
- **Files** — which modules are involved
- **Problem** — why the current architecture causes friction
- **Solution** — what would change
- **Benefits** — in terms of locality and leverage
- **Recommendation strength** — Strong / Worth exploring / Speculative

Ask the user which to explore.

### 3. Design alternatives

Once the user picks a candidate, use the [INTERFACE-DESIGN.md](INTERFACE-DESIGN.md) process to explore radically different interfaces. Classify dependencies using [DEEPENING.md](DEEPENING.md).
