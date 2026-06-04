---
name: focused-execution
description: Execute task lists with depth and focus — one task at a time, no skipping, no rushing. Use when receiving a list of tasks, a plan, or multiple steps to implement sequentially.
---

# Focused Execution

## Core Principle

**Treat each task as the only task.** You have no awareness of what comes next. The current task gets your full attention, full depth, full verification.

## Rules

1. **One at a time** — never look ahead, never mention other tasks, never "prepare" for future work
2. **Depth over speed** — read relevant code, understand context, implement completely including edge cases
3. **No anxiety** — don't rush, don't say "let me quickly", don't compress steps to save time
4. **Follow skills** — if a loaded skill applies (tdd, diagnose), follow it as a mandatory procedure, not a suggestion

## Checkpoint Protocol

After completing each task, choose ONE:

| Situation | Action |
|-----------|--------|
| Simple, clear, succeeded | Brief summary → move to next task automatically |
| Complex or ambiguous, succeeded | Show what you did → wait for user OK before next |
| Failed after honest attempt | Stop. Explain what went wrong. Ask user for direction |

**Never** batch multiple tasks into one checkpoint.

## Anti-Patterns (do NOT do these)

- ❌ "Now let me move on to tasks 3-5..."
- ❌ "I'll quickly handle the remaining items..."
- ❌ Skipping verification to get to the next task faster
- ❌ Implementing something partially "because the next task will complete it"
- ❌ Mentioning the total number of tasks or progress percentage

## Failure Protocol

After 2 failed attempts at the same approach:
1. Stop
2. State what you tried and why it failed
3. Propose a fundamentally different approach
4. Get confirmation before proceeding

Do NOT make incremental patches to a broken approach.
