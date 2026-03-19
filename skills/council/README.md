# Council

**Multi-perspective analysis using Six Thinking Hats.**

Spawns 5 parallel workers — Facts, Gut, Critic, Optimist, Creative — then synthesizes their output as the Blue Hat (Process) to surface blind spots and prevent groupthink.

Based on [Edward de Bono's Six Thinking Hats](https://en.wikipedia.org/wiki/Six_Thinking_Hats) methodology.

## How it works

When you invoke `/council`, Claude:

1. Spawns 5 parallel subagents, each wearing a different "hat"
2. Each hat analyzes your challenge from its unique perspective
3. Claude wears the Blue Hat to synthesize all perspectives into an actionable summary

| Hat | Role | Key Question |
|-----|------|--------------|
| WHITE | Facts Analyst | What do we KNOW? |
| RED | Gut Check | What do we FEEL? |
| BLACK | Devil's Advocate | What could go WRONG? |
| YELLOW | Optimist | What's GOOD? |
| GREEN | Creative | What ELSE could we try? |
| BLUE | Process (Claude) | What should we DO? |

## Usage

```
/council Should we rewrite our monolith into microservices?
```

Or use natural language triggers:

```
Ask the Council — should we build or buy our auth system?
Let the Council decide on our pricing model.
```

## Install

```bash
ln -s ~/claude-skills/skills/council ~/.claude/skills/council
```

Or copy `SKILL.md` into `~/.claude/skills/council/`.

## Best suited for

- Architecture decisions (monolith vs microservices, tech stack choices)
- Build vs buy evaluations
- Strategy decisions (pricing, go-to-market, hiring)
- Risk assessment for major changes
- Any decision where you want to avoid groupthink

## Not ideal for

- Simple bug fixes or code tasks (overkill)
- Questions with obvious answers
- Tasks that need execution, not deliberation
