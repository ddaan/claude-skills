# Claude Skills

Custom skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Skills

| Skill | Description |
|-------|-------------|
| [council](skills/council/) | Multi-perspective analysis using Six Thinking Hats. Spawns 5 parallel workers then synthesizes with Blue Hat. |

## Install

### All skills

```bash
git clone https://github.com/ddaan/claude-skills.git ~/claude-skills

# Symlink all skills at once
for skill in ~/claude-skills/skills/*/; do
  ln -s "$skill" ~/.claude/skills/"$(basename "$skill")"
done
```

### Single skill

```bash
git clone https://github.com/ddaan/claude-skills.git ~/claude-skills

# Symlink just one
ln -s ~/claude-skills/skills/council ~/.claude/skills/council
```

### Without cloning

Copy the `SKILL.md` from any skill directory into `~/.claude/skills/<skill-name>/SKILL.md`.

## Structure

```
skills/
  council/
    SKILL.md        # Skill definition (required)
    README.md       # Documentation
  your-skill/
    SKILL.md
    README.md
```

## License

MIT
