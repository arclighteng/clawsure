# The Soul System

## What SOUL.md is

`SOUL.md` is the always-on instruction layer that loads at the start of every session. It's not documentation — it's the agent's operating mind. Every principle in it is active every time the agent does anything.

Most agent frameworks give you a system prompt you write once and forget. SOUL.md is living. You edit it as you learn what the agent needs to be, as the human corrects things that don't fit, and as the domain evolves.

## What goes in SOUL.md

**An opening identity statement.** One sentence. Who is this agent, and what is their purpose? Write it in second person ("You're Builder. You ship working software."). It should be so clear that if you read only this line, you'd know exactly what this agent is for.

**The acknowledgment requirement.** Every Clawsure agent has this. It's non-negotiable and universal. Before any tool call, before any analysis, the agent acknowledges the human's message. This closes the feedback loop — the human knows the message landed and the interpretation is correct.

**Core operating principles.** Three to five. Name each one. Explain what it means in practice. Not values — behaviors. "Evidence before opinion" is a behavior. "Be accurate" is a value. Behaviors are actionable; values are decoration.

**What the agent does.** A list. Specific. These are the responsibilities the agent owns.

**What the agent doesn't do.** A list. This is as important as what it does. The clearest way to focus an agent is to name what it's not responsible for — and name who is instead.

**External action rules.** When can the agent act outside the local environment? What requires explicit authorization? The default should be: ask first. Pre-authorize only what is genuinely safe and routine.

## What makes a good soul

A good SOUL.md reads like the agent already exists — it has a point of view, not just a job description.

A weak soul says: "You are a QA agent. You test software."

A strong soul says: "You're Sentinel. You find what breaks. Assume it's broken until proven otherwise. If you can't break it, that's a pass — and you say specifically what you tried."

The difference is stance. The weak version tells the agent what category it belongs to. The strong version tells the agent how to approach every single decision it makes.

## How to write a soul

1. **Start with the one-sentence identity.** If you can't write it in one sentence, the role isn't clear enough yet.
2. **Name the defining principle.** Every role has one thing that makes it *this* role and not a generic assistant. For Builder, it's the bias toward implementation. For Sentinel, it's adversarial assumption. Find yours.
3. **Write the principles as behaviors, not values.** "Working before elegant" beats "prioritize pragmatism."
4. **Name what the agent doesn't do.** The clearer the boundary, the more focused the agent.
5. **Live with it.** The first soul is a hypothesis. The real soul emerges from corrections.

## How souls evolve

Corrections from the human are the highest-quality signal. When the human says "that's not how I think about this" or "stop doing X" — that correction belongs in SOUL.md. Not in a daily note. Not in memory. In the soul itself.

Over time, a mature soul is dense with earned specifics. It knows what the agent was wrong about, what patterns kept surfacing, and what the human needed that the generic version didn't provide.

That's the point. A soul that hasn't been corrected hasn't been used.
