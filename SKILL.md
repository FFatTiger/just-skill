---
name: just
description: Use only when the user explicitly invokes just-mode or asks to skip ceremony, avoid research, avoid planning, avoid extra skills, avoid subagents, avoid explore agents, avoid TODOs, stop overthinking, or directly execute a simple requested action. Do not use by default or infer it from ordinary tasks.
---

# Just

## Overview

Just mode is an anti-ceremony workflow for agents. When the user explicitly asks for it, do the requested work directly with the smallest safe action path.

Core principle: obey the user's request for low ceremony without becoming reckless.

## Activation

Use this skill only when the user explicitly says something like:

- `/just`, `just`, `just mode`
- `直接做`, `直接改`, `开干`, `别废话`
- `不要调研`, `不要 planning`, `不要 spec`, `不要 TODO`
- `别调用其他 skill`, `别走流程`, `stop overthinking`

Do not activate this skill merely because the task looks simple. If the user did not ask for just-mode behavior, use the normal workflow.

## Rules

When active:

1. Do not brainstorm, write specs, enter plan mode, or create TODO lists.
2. Do not dispatch subagents, Explore agents, research agents, review agents, or parallel agents.
3. Do not perform broad codebase exploration; inspect only the exact files, commands, or state needed for the task.
4. Do not ask clarifying questions unless the request is impossible or dangerous without one.
5. Do not invoke other process skills unless required by a higher-priority system/developer rule.
6. Make the smallest change that satisfies the request.
7. Verify with the fastest command that proves the change worked.
8. Report only what changed and the verification result.

## Safety Boundary

Just mode does not authorize destructive or externally visible actions.

Still ask before:

- deleting data, files, branches, databases, or infrastructure
- force pushing, resetting, cleaning, or overwriting uncommitted work
- publishing, sending messages, opening/closing PRs or issues
- changing secrets, permissions, billing, or shared production systems

If verification is impossible or would be too expensive, say exactly that and give the next best evidence.

## Response Style

Use terse status updates only when needed. Final response should be short:

```text
已完成：<what changed>。
验证：<command/result>。
```

Avoid long explanations, alternatives, design discussion, or summaries of obvious steps.

## Common Mistakes

| Mistake | Correct behavior |
|---|---|
| Treating just mode as permission to skip safety | Keep safety boundaries |
| Running broad research first | Inspect only what is necessary |
| Creating a plan or TODO list | Directly edit or execute |
| Asking preference questions | Pick the obvious minimal path |
| Invoking every relevant skill | Suppress process skills unless higher-priority rules force them |
| Dispatching subagents or Explore agents | Work in the current agent with targeted reads/searches only |
| Starting broad codebase discovery | Use the narrowest file read or search needed |
| Reporting a long narrative | Give changed/result only |
