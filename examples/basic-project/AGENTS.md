# AGENTS.md

**Project:** TaskTracker CLI  
**Last updated:** 2026-01-10  
**Maintainer:** Alex Chen

---

## Project Overview

A minimal command-line task tracker for developers who want to stay in the terminal. Supports projects, tags, priorities, and due dates. Stores data in a local SQLite database.

**Tech stack:** Python 3.11 + SQLite + Click (CLI framework) + pytest  
**Primary language:** Python  
**Entry point:** `src/tasktracker.py`  
**Test command:** `pytest`

---

## Agent Behaviour Rules

### Do
- [ ] Read README.md before touching anything
- [ ] Run `pytest` before claiming a task is complete
- [ ] Update `CODEX_HANDOFF.md` after each session
- [ ] Follow PEP 8 style (enforced by `ruff`)
- [ ] Ask before adding new dependencies beyond the core stack (Click, SQLite, pytest, ruff)
- [ ] Prefer small, focused changes over large refactors

### Don't
- [ ] Commit directly to `main`
- [ ] Delete `.tasks.db` without confirming it's the local dev database
- [ ] Skip tests because "they'll pass"
- [ ] Add GUI or web interface code — this is CLI-only by design

---

## Project Conventions

### Directory structure

```
tasktracker/
  src/              — Application source code
  tests/            — pytest test files (mirror src/ structure)
  docs/             — User-facing documentation
  scripts/          — Build and release scripts
```

### Naming conventions
- Files: `snake_case.py`
- Functions: `verb_noun` (e.g. `create_task`, `list_tasks`)
- Classes: `PascalCase`
- Branches: `feature/description`, `fix/issue-number`

### Key dependencies
- `click` — CLI framework
- `tabulate` — Pretty table output for `list` command
- `pytest` — Testing framework
- `ruff` — Linter and formatter

### Environment setup

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
pytest
```

---

## Context Files

- `README.md` — Project overview and setup
- `CODEX_HANDOFF.md` — Current session state and next steps
- `docs/commands.md` — Full command reference

---

## Current Priorities

1. Add `--json` output flag to `list` command
2. Fix bug where `--due` accepts invalid dates silently
3. Add tab completion for shell (bash, zsh)

---

## Known Issues

- Date parsing accepts "2026-02-30" without error (just stores as March)
- `--project` filter is case-sensitive when it shouldn't be
- No export/import functionality yet

## Recent Decisions

- Decided against JSON file storage early on — SQLite is fine for local single-user tool
- Using `datetime` objects internally, ISO 8601 strings in CLI interface
