# Roadmap

## Current version: 1.0.0

This repo is intentionally minimalist. Future additions will only happen if they solve real problems for multiple users.

---

## Released

### v1.0.0 — Initial templates
- AGENTS.md template
- SKILL.md template
- CODEX_HANDOFF.md template
- GOAL_PROMPT.md template
- POST_RUN_REPORT.md template
- Safe session, continuity, and handoff checklists
- Three example projects
- Issue templates for contributions

---

## Under consideration

These are ideas, not commitments. They may be added, rejected, or replaced based on user feedback.

| Idea | Rationale | Status |
|---|---|---|
| VS Code snippets for quick template insertion | Speeds up template adoption for VS Code users | Needs demand signal |
| Claude Code specific notes | Claude Code is popular; compatibility notes would help | Requires testing and validation |
| Aider compatibility guide | Aider users may need slightly different conventions | Needs community input |
| Template versioning guidance | How to evolve templates without breaking existing handoffs | Needs real-world usage |
| CI checklist template | What to verify before letting an agent commit to `main` | Needs refinement |

## Not planned

These are out of scope for this repo. They might be their own repos, or they might never happen.

- A CLI tool to generate handoff files
- A web dashboard for tracking agent sessions
- Integration with specific project management tools (Jira, Linear, etc.)
- Automatic handoff generation from agent logs
- A framework or SDK around these templates

---

## Decisions log

| Date | Decision | Reason |
|---|---|---|
| 2026-06-09 | Keep V1 documentation-only | Keeps the kit simple, low-risk, and easy to adopt without installing tools |
| 2026-06-09 | Focus on project continuity, not agent orchestration | Keeps the repo distinct from protocol/framework-style agent handoff tools |
| 2026-06-09 | Use examples before adding automation | Lets the templates prove their value before introducing executable tooling |

## How to influence the roadmap

If you want something on this list, open an issue explaining:

1. The problem you hit
2. How you tried to solve it with the current templates
3. What addition or change would have helped

Requests with concrete use cases get priority over abstract ideas.
