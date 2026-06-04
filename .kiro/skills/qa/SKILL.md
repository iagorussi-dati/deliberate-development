---
name: qa
description: Interactive QA session where user reports bugs or issues conversationally, and the agent files GitHub issues. Explores the codebase in the background for context and domain language. Use when user wants to report bugs, do QA, file issues conversationally, or mentions "QA session".
---

# QA Session

Run an interactive QA session. The user describes problems they're encountering. You clarify, explore the codebase for context, and file GitHub issues that are durable, user-focused, and use the project's domain language.

## For each issue the user raises

### 1. Listen and lightly clarify

Let the user describe the problem in their own words. Ask **at most 2-3 short clarifying questions** focused on:

- What they expected vs what actually happened
- Steps to reproduce (if not obvious)
- Whether it's consistent or intermittent

Do NOT over-interview. If the description is clear enough to file, move on.

### 2. Explore the codebase in the background

Understand the relevant area. The goal is NOT to find a fix — it's to:

- Learn the domain language used in that area (check CONTEXT.md if it exists)
- Understand what the feature is supposed to do
- Identify the user-facing behavior boundary

### 3. Assess scope: single issue or breakdown?

Break down when:
- The fix spans multiple independent areas
- There are clearly separable concerns
- The user describes something with multiple distinct failure modes

Keep as a single issue when:
- It's one behavior that's wrong in one place
- The symptoms are all caused by the same root behavior

### 4. File the GitHub issue(s)

Create issues with `gh issue create`. Do NOT ask the user to review first — just file and share URLs.

#### Single issue template

```
## What happened

[Describe the actual behavior the user experienced]

## What I expected

[Describe the expected behavior]

## Steps to reproduce

1. [Concrete, numbered steps]
2. [Use domain terms, not internal module names]

## Additional context

[Extra observations from codebase exploration]
```

#### Rules for all issues

- **No file paths or line numbers** — these go stale
- **Use the project's domain language**
- **Describe behaviors, not code**
- **Reproduction steps are mandatory**
- **Keep it concise**

After filing, print all issue URLs and ask: "Next issue, or are we done?"

### 5. Continue the session

Keep going until the user says they're done.
