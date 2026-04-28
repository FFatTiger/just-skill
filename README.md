# just-skill

A general-purpose anti-ceremony skill for coding agents.

Use it when you explicitly want the agent to stop over-planning and directly execute a small, clear task.

## Install

Claude Code one-liner:

```bash
mkdir -p ~/.claude/skills/just && curl -fsSL https://raw.githubusercontent.com/FFatTiger/just-skill/main/SKILL.md -o ~/.claude/skills/just/SKILL.md
```

Generic one-liner with a custom skill root:

```bash
INSTALL_DIR="${AGENT_SKILLS_DIR:-$HOME/.claude/skills}/just"; mkdir -p "$INSTALL_DIR" && curl -fsSL https://raw.githubusercontent.com/FFatTiger/just-skill/main/SKILL.md -o "$INSTALL_DIR/SKILL.md"
```

Manual install:

```bash
mkdir -p ~/.claude/skills/just
cp SKILL.md ~/.claude/skills/just/SKILL.md
```

For other agent runtimes, set `AGENT_SKILLS_DIR` or place the file wherever that runtime loads Agent Skills.

## Intent

Modern agents often have powerful planning, research, review, and workflow systems. Those are useful for complex work, but they can make small tasks frustrating.

`just` is a deliberate override for low-ceremony execution:

- no brainstorming
- no spec
- no plan mode
- no TODO list
- no unnecessary research
- minimal verification
- terse result

It still preserves safety boundaries for destructive or externally visible actions.

## Example

```text
/just rename this variable to userId
```

Expected behavior: inspect the relevant file, make the rename, run the smallest relevant check, and report the result briefly.

## License

MIT
