# Agent Communication

## The model

Clawsure agents are designed to communicate peer-to-peer with no fixed lead. There is no permanent orchestrator — Coordinator plays that role when needed, but any agent can initiate work with another.

This is different from hub-and-spoke models where a central agent dispatches all work. In Clawsure, the agents know each other exists and can communicate directly when the task warrants it.

## How communication works

The mechanism depends on the runner you're using. Clawsure is language-agnostic — it defines the *structure* and *conventions*, not the implementation.

**Common patterns:**

- **Direct message** — one agent sends a task or question to another. The receiving agent processes it and replies. No coordinator required.
- **Routed via coordinator** — the human asks Coordinator; Coordinator delegates to the right agent(s), collects results, synthesizes.
- **Autonomous initiation** — an agent identifies work that's ready for another agent and sends it without being told. (Example: Builder finishes a feature and sends it to Sentinel for validation.)

## What agents know about each other

Each agent's `AGENTS.md` has a team roster: every agent's name, role, and workspace path. This is what an agent uses to decide who to send work to and where to find their workspace.

Keep `AGENTS.md` up to date when you add, rename, or retire agents.

## Communication conventions

**Acknowledgment first.** When an agent receives a task from another agent, the same acknowledgment rule applies as with human messages — acknowledge before acting.

**Scope what you send.** When routing work to another agent, be specific about what you need back. "Validate this" is worse than "run the test suite and check the `/api/status` endpoint. Report PASS/FAIL with specifics."

**Route results back.** If Coordinator delegated the work, results go back to Coordinator for synthesis. If the human delegated directly, results go to the human.

**No silent handoffs.** If you send work to another agent, the human should know — either through a message or through the next synthesis. Nothing disappears into the agent network without a trace.

## Identity in communication

Clawsure's core differentiator is that agents carry their identity across sessions. This matters for communication: when Builder receives work from Coordinator, Builder knows who Coordinator is, what their working relationship is, and what the history of the project is.

This is the layer that stateless workers don't have. A fresh spawn knows nothing about the context that preceded it. A Clawsure agent knows the history — and communicates with that knowledge active.

## Extending communication

The specific tools for inter-agent messaging (message queues, shared files, API calls, MCP tools) are outside Clawsure's scope — they depend on your infrastructure. Clawsure provides the *identity layer* that makes those communications meaningful. The transport is yours to choose.

What Clawsure gives you: agents that know each other, have accumulated context, and carry that context into every exchange. What you wire them together with is up to you.
