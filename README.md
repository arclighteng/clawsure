> **⚠️ DEPRECATED (2026-06-25)**
>
> Clawsure is no longer actively developed. The concepts it explored — persistent agent identity,
> per-agent memory, and role-based personas — have been absorbed into other systems:
>
> - **Agent personas** → [CSuite](https://github.com/arclighteng/csuite) subagent definitions
> - **Persistent memory** → Claude Code's built-in auto-memory system
> - **Role-based agents** → Claude Code's `~/.claude/agents/` directory (80+ role agents)
>
> This repo is preserved as a reference for the identity-layer pattern. No further commits are planned.

# Clawsure

**Persistent named agents with souls, memory, and voice.**

Most AI agent frameworks give you workers — stateless processes that spin up, do a job, and get cleaned up. Each run is fresh. No memory of what came before, no accumulated lessons, no identity that persists when the session ends.

Clawsure is the layer above that.

In programming, a **closure** is a function that captures its surrounding context and keeps it alive beyond the scope that created it. Clawsure agents work the same way — they close over their context (their soul, their memory, their understanding of the work) and carry it forward across every session.

---

## What makes a Clawsure agent different

| Stateless worker | Clawsure agent |
|---|---|
| Spawns fresh each run | Carries memory across sessions |
| No identity | Named, with a defined personality |
| Task-scoped | Ongoing collaborator |
| Interchangeable | Irreplaceable — knows the history |
| Garbage collected | Persistent by design |

---

## How it works

Each agent lives in its own directory with five core files:

```
agents/
└── coordinator/
    ├── IDENTITY.md   — who this agent is (name, role, vibe)
    ├── SOUL.md       — operating principles, voice, how it thinks
    ├── USER.md       — who the human is and what they care about
    ├── AGENTS.md     — workspace rules, team roster, protocols
    └── memory/
        ├── MEMORY.md          — curated long-term memory index
        └── YYYY-MM-DD.md      — daily session notes
```

These files are loaded as context at the start of every session. The agent picks up exactly where it left off.

---

## Default agent roster

Clawsure ships with five agents. Rename them, rewrite their souls, add more — the structure is yours.

| Agent | Role | Default focus |
|---|---|---|
| `coordinator` | Orchestrator | Delegates, tracks, synthesizes across agents |
| `builder` | Engineer | Writes code, builds features, ships |
| `analyst` | Researcher | Data, research, investigation, synthesis |
| `writer` | Communicator | Docs, content, copy, voice |
| `sentinel` | QA/Security | Validation, adversarial testing, failure analysis |

---

## Quick start

```bash
# Clone and enter
git clone https://github.com/arclighteng/clawsure.git
cd clawsure

# Fill in USER.md for each agent (who is the human they work for?)
# Edit SOUL.md to shape each agent's personality and operating principles
# Start a session with any Claude-compatible runner pointed at an agent's directory
```

The files are plain markdown. No dependencies. No build step. Any runner that can load a directory of markdown files as context can run a Clawsure agent.

---

## Agent communication

Clawsure agents are designed to communicate peer-to-peer with no fixed lead. See [docs/agent-communication.md](docs/agent-communication.md) for patterns and protocols.

---

## The soul system

SOUL.md is the most important file. It's the always-on instruction layer that defines how an agent thinks, speaks, and prioritizes. The identity in SOUL.md is what makes an agent *this agent* rather than a generic assistant.

See [docs/soul-system.md](docs/soul-system.md) for how to write a good soul.

---

## Memory system

Agents accumulate memory across sessions in two layers:

- **Daily notes** (`memory/YYYY-MM-DD.md`) — what happened in a session
- **Long-term memory** (`memory/MEMORY.md`) — curated, indexed, persistent facts the agent carries forward

See [docs/memory-system.md](docs/memory-system.md) for how memory is structured and when to write to it.

---

## Philosophy

> Complexity earns its keep only when it produces value. The persistent-identity layer earns it — because when anyone can spin up parallel agents that message each other, the differentiator is what those agents carry forward when the session ends.

Clawsure bets on the named-agent character layer. The orchestration layer is commodity. What those agents *are* is not.

---

## License

MIT
