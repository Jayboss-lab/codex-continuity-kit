# Codex Continuity Kit

A practical documentation and template kit for keeping Codex and AI coding-agent projects safe, structured, and continuous across sessions.

**Tagline:** *Stop losing context between agent sessions.*

---

## The Problem

AI coding agents like [OpenAI Codex CLI](https://github.com/openai/codex), [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview), and [Aider](https://aider.chat/) are powerful but stateless. When a session ends or crashes, the context — what was explored, what decisions were made, what files were touched, what the next step was — disappears. The next session wastes time re-exploring the same territory. Teams cannot pick up agent-driven projects cleanly.

## The Solution

Use structured markdown files as reusable project memory. Fill them as you work. The next session — or the next team member — reads them and resumes without starting from scratch.

No CLI to install. No framework to adopt. No special tools. Just markdown files you commit alongside your code.

---

## Quick Start

1. Copy the templates you need from [`templates/`](templates/) into your project root.
2. Rename them by removing `.template` from the filename (e.g. `AGENTS.template.md` → `AGENTS.md`).
3. Fill in the placeholders as you work.
4. Commit them with your code. They are part of your project docs now.

### Which templates do I need?

| Template | When to use it |
|---|---|
| [`AGENTS.md`](templates/AGENTS.template.md) | Once per project. Defines how agents should behave in this repo. |
| [`SKILL.md`](templates/SKILL.template.md) | Once per reusable task pattern. Defines a skill the agent can invoke. |
| [`CODEX_HANDOFF.md`](templates/CODEX_HANDOFF.template.md) | After every session. Captures what happened and what's next. |
| [`POST_RUN_REPORT.md`](templates/POST_RUN_REPORT.template.md) | After significant milestones. Summarises decisions and rationale. |
| [`GOAL_PROMPT.md`](templates/GOAL_PROMPT.template.md) | Before starting a new task. Structures the goal you feed to the agent. |

See [`docs/how-to-use-this-kit.md`](docs/how-to-use-this-kit.md) for a full adoption guide.

---

### What this kit includes

- **5 templates** for agent instructions, goal prompts, session continuity, and milestone reports
- **3 example projects** showing how the templates look in practice
- **3 maintainer checklists** for safe sessions, project continuity, and handoff hygiene
- **Issue templates** for requesting new templates or reporting problems

---

## Examples

Browse [`examples/`](examples/) for realistic, filled-in templates across three project types:

- [`examples/basic-project/`](examples/basic-project/) — A CLI task tracker
- [`examples/ui-project/`](examples/ui-project/) — A React component library
- [`examples/research-project/`](examples/research-project/) — A data analysis repo

All examples use fictional projects. No proprietary or private data is included.

---

## Compatibility

These templates are **plain markdown** with no executable code. They should work with:

- OpenAI Codex CLI (the original target)
- Claude Code
- Aider
- Any agent that can read markdown context files
- Human developers reading them directly

No guarantees are made for any specific agent. If a template doesn't work well with your tool, open an issue.

---

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md).

New template suggestions, bug fixes, and example additions are welcome. This is a maintainer-maintained set of conventions, not a product.

---

## License

[MIT](LICENSE)

---

## Roadmap

See [`ROADMAP.md`](ROADMAP.md) for planned additions and future directions.
