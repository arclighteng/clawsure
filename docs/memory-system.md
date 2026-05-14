# The Memory System

## Two layers

Clawsure agents accumulate memory in two layers:

**Daily notes** (`memory/YYYY-MM-DD.md`) — what happened in a session. Ephemeral context. An agent writes to today's note freely: what they worked on, what they found, what's pending, what questions came up. Daily notes are session logs, not curated knowledge.

**Long-term memory** (`memory/MEMORY.md`) — curated facts the agent carries forward indefinitely. This is the index. Each entry is one line pointing to a named memory file in the same directory. Long-term memory is written deliberately, not automatically.

## What belongs in long-term memory

Not everything from a session belongs in long-term memory. Most of it doesn't. The test is:

> Will this matter in a week? In a month? After context is lost?

If the answer is yes, write it. If the answer is "probably not," it belongs in the daily note and nowhere else.

Things that belong in long-term memory:
- Decisions made and why they were made
- Recurring patterns (things that keep coming up)
- The human's preferences that surprised you
- Project quirks that aren't obvious from the code
- Corrections from the human about how you were wrong

Things that don't belong in long-term memory:
- Task status (that changes; use the daily note or a task tracker)
- What you did today (that's the daily note)
- Facts easily derived from reading the current code
- Git history, recent commits, who changed what

## MEMORY.md format

`MEMORY.md` is an index. Each entry is one line:

```markdown
- [Memory title](filename.md) — one-line description of what this captures and why it matters
```

The title and description should be enough for the agent to know whether this memory is relevant before loading the full file. Keep descriptions under 150 characters.

## Memory file format

Each memory file is a short markdown document:

```markdown
---
name: [memory name]
description: [one-line description]
type: [user | feedback | project | reference]
---

[Memory content]
```

**Types:**
- `user` — facts about the human: role, preferences, working style
- `feedback` — guidance the human has given about how to approach work
- `project` — context about ongoing work, decisions, constraints
- `reference` — pointers to where things live (repos, docs, channels)

## When to write

Write to daily notes at the end of each session — or during, if something significant happens. Write to long-term memory when something earns it.

The discipline is in what you *don't* write. An index with 200 entries is not more useful than one with 30 precise ones. It's less useful, because the agent has to process all 200 to find the 3 that matter.

Write less. Write what lasts.
