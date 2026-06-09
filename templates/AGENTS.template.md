# AGENTS.md

**Project:** `[PROJECT_NAME]`  
**Last updated:** `[YYYY-MM-DD]`  
**Maintainer:** `[NAME or TEAM]`

---

## Project Overview

A brief description of what this project does and who uses it.

**Tech stack:** `[e.g. Python 3.11 + FastAPI + PostgreSQL + Docker]`  
**Primary language(s):** `[e.g. Python, TypeScript]`  
**Entry points:** `[e.g. src/main.py, apps/web/pages/index.tsx]`  
**Test command:** `[e.g. pytest, npm test, go test ./...]`

---

## Agent Behaviour Rules

When working in this repo, agents should:

### Do
- [ ] Read the README before touching anything
- [ ] Run tests before claiming a task is complete
- [ ] Update `CODEX_HANDOFF.md` after each session
- [ ] Follow the existing code style (see `.editorconfig` or linter config if present)
- [ ] Ask before adding new dependencies
- [ ] Prefer small, focused changes over large refactors

### Don't
- [ ] Commit directly to `main` unless explicitly told to
- [ ] Delete files without explaining why in the handoff
- [ ] Skip tests because "they'll pass"
- [ ] Add configuration without documenting it
- [ ] Touch files outside the scope of the current task without asking

---

## Project Conventions

### Directory structure
Brief explanation of the top-level directories and where things belong.

```
`[PROJECT_NAME]/`
  src/          — Application source code
  tests/        — Test files (mirror src/ structure)
  docs/         — Project documentation (not agent handoffs)
  scripts/      — Build, deploy, and utility scripts
  config/       — Environment-specific configuration files
```

### Naming conventions
- Files: `[e.g. snake_case for Python, camelCase for TS]`
- Functions: `[e.g. verb_noun]`
- Branches: `[e.g. feature/description, fix/issue-number]`

### Key dependencies
- `[dependency-name]` — `[what it's for]`
- `[dependency-name]` — `[what it's for]`

### Environment setup
How to get the project running locally:

```bash
# Example commands
[YOUR_SETUP_COMMANDS_HERE]
```

---

## Context Files

Agents should read these files before starting work:

- `README.md` — Project overview and setup
- `CODEX_HANDOFF.md` — Current session state and next steps
- `[OTHER_RELEVANT_FILES]` — `[e.g. ARCHITECTURE.md, API_SPEC.md]`

---

## Current Priorities

What the team is working on right now, in order:

1. `[Priority 1: e.g. Fix failing payment integration tests]`
2. `[Priority 2: e.g. Migrate auth module to OAuth 2.0]`
3. `[Priority 3: e.g. Performance optimisation for search route]`

---

## Known Issues

- `[Issue 1: e.g. Database migration 004 fails on Windows CI]`
- `[Issue 2: e.g. Rate limiting not implemented on public endpoints]`

## Recent Decisions

- `[Decision: e.g. Switched from REST to GraphQL for internal API]`
- `[Decision: e.g. Using UUIDv7 for all new primary keys]`
