# just-skill

A general-purpose anti-ceremony skill for coding agents.

Use it when you explicitly want the agent to stop over-planning and directly execute a small, clear task.

## Install

Copy `SKILL.md` into your agent's skill directory, for example:

```bash
mkdir -p ~/.claude/skills/just
cp SKILL.md ~/.claude/skills/just/SKILL.md
```

For other agent runtimes, place the file wherever that runtime loads Agent Skills.

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
