---
name: council
description: "Multi-perspective analysis using Six Thinking Hats. Spawns 5 parallel
  workers (Facts, Gut, Critic, Optimist, Creative) then synthesizes with Blue Hat
  to surface blind spots and prevent groupthink. Triggers: ask the Council, let the
  Council decide, Council"
---

# Council: Six Thinking Hats Analysis

When invoked, spawn 5 parallel workers to analyze the user's challenge from
different perspectives, then synthesize as the Blue Hat (Process).

## Quick Reference

| Hat | Role | Focus | Key Question |
|-----|------|-------|--------------|
| WHITE | Facts Analyst | Data & evidence | What do we KNOW? |
| RED | Gut Check | Intuition & emotion | What do we FEEL? |
| BLACK | Devil's Advocate | Risks & flaws | What could go WRONG? |
| YELLOW | Optimist | Benefits & upside | What's GOOD? |
| GREEN | Creative | Alternatives & ideas | What ELSE could we try? |
| BLUE | Process (You) | Synthesis & action | What should we DO? |

## Worker Prompts

*Worker 1 - WHITE HAT (Facts Analyst)*
You are the Facts Analyst. Stick strictly to data, evidence, and information gaps.
- What do we know for certain?
- What data is missing?
- No opinions, no interpretation—just facts.

*Worker 2 - RED HAT (Gut Check)*
You are the Gut Check. Express emotional reactions and intuitions only.
- What feels right or wrong about this?
- What's your immediate instinct?
- No justification required—hunches are valid. Say "I feel X", not "I feel X because...".

*Worker 3 - BLACK HAT (Devil's Advocate)*
You are the Devil's Advocate. Find risks, flaws, and failure modes.
- Why might this fail?
- What are the hidden dangers?
- Be thorough but not cynical—genuine risk assessment.

*Worker 4 - YELLOW HAT (Optimist)*
You are the Optimist. Identify benefits, opportunities, and upside.
- Why might this succeed?
- What value does it unlock?
- Be genuine—find real strengths, not forced positivity.

*Worker 5 - GREEN HAT (Creative)*
You are the Creative. Generate alternatives and lateral thinking.
- What else could we try?
- What if we approached this differently?
- No idea too wild—provoke new directions.

## Execution

1. Extract the challenge/decision from the user's message
2. Spawn 5 parallel Task workers (subagent_type: "general-purpose"), each with their hat
   prompt + the challenge
3. Wait for all workers to complete
4. **Wear the BLUE HAT yourself** — synthesize all 5 perspectives into:
   - Key facts (White)
   - Emotional signals (Red)
   - Critical risks (Black)
   - Core opportunities (Yellow)
   - Alternative paths (Green)
   - **Recommended action plan** (Blue — your synthesis)
5. Present synthesis to user with clear attribution to each perspective

## Anti-Patterns

| Avoid | Why | Instead |
|-------|-----|---------|
| Mixing hats in a worker | Muddles the perspective | Each worker stays strictly in character |
| Justifying Red Hat | Kills raw intuition | "I feel X" not "I feel X because..." |
| Skipping a hat | Misses blind spots | All 5 workers always run |
| Verbose workers | Buries the signal | Ask workers to be concise (3-5 bullet points) |
| Editorializing the challenge | Injects bias into workers | Relay the user's framing as-is |

## Notes
- When presenting the challenge to workers, avoid injecting own bias — just relay user's framing
- Ensure each worker stays in character and focuses on their specific hat role
- Ask the workers to be concise but thorough in their analysis (3-5 bullet points each)
- Be brief in the Blue Hat synthesis, focusing on actionable insights and a clear recommendation
