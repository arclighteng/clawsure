# Getting Started with Clawsure

## 1. Clone the repo

```bash
git clone https://github.com/arclighteng/clawsure.git
cd clawsure
```

## 2. Fill in USER.md for each agent

`USER.md` tells each agent who they're working for. Open each agent's `USER.md` and fill in:

- The human's name and preferred handle
- Timezone and contact method
- Working style (how they communicate, what they value)
- Active projects

Every agent gets the same `USER.md` to start — you can diverge them later if an agent needs a different lens on the human's context.

```bash
# Edit for each agent:
nano agents/coordinator/USER.md
nano agents/builder/USER.md
# ... etc
```

## 3. Shape each agent's soul

`SOUL.md` is the most important file. It loads as always-on context in every session. The default souls are functional starting points — they define the role and operating principles, but they don't know your specific domain, your human's specific voice, or the quirks of your specific codebase.

Spend time here. The soul is the differentiator.

```bash
nano agents/builder/SOUL.md  # Add domain-specific principles
nano agents/writer/SOUL.md   # Add the human's voice profile
nano agents/sentinel/SOUL.md # Add known failure patterns to watch for
```

## 4. Start a session

Point your Claude-compatible runner at an agent's directory. The runner should load:

1. `SOUL.md` — always on, every session
2. `IDENTITY.md` — who this agent is
3. `USER.md` — who the human is
4. `AGENTS.md` — workspace rules and team roster
5. `memory/MEMORY.md` — curated long-term memory

At the end of each session, the agent should write a daily note to `memory/YYYY-MM-DD.md` and update `memory/MEMORY.md` with anything worth keeping long-term.

## 5. Add your own agents

The default five cover the core roles. To add a new agent:

```bash
mkdir -p agents/your-agent/memory
cp templates/IDENTITY.md agents/your-agent/IDENTITY.md
cp templates/SOUL.md agents/your-agent/SOUL.md
cp templates/USER.md agents/your-agent/USER.md
cp templates/AGENTS.md agents/your-agent/AGENTS.md
cp templates/memory/MEMORY.md agents/your-agent/memory/MEMORY.md
```

Then fill in each file.

## 6. Update the team roster

When you add or rename an agent, update `AGENTS.md` in each existing agent's directory so everyone knows who's on the team.
