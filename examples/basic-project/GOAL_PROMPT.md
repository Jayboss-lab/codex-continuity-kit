# GOAL_PROMPT.md

**Date:** 2026-01-09  
**Project:** TaskTracker CLI  
**Session:** 12  
**Priority:** HIGH

---

## Goal

Add a `--json` output flag to the `list` command that outputs tasks as a JSON array instead of a formatted table.

---

## Background

Users want to pipe task output to other tools (jq, grep, custom scripts). The current table format is human-readable but not machine-parseable. The `tabulate` library is deeply coupled to the current `list` command.

---

## Acceptance Criteria

- [ ] `tasktracker list --json` outputs a valid JSON array of task objects
- [ ] JSON output works with existing filters (`--project`, `--tag`, `--priority`)
- [ ] JSON output is mutually exclusive with `--format` (table format flag)
- [ ] Tests verify JSON output structure and filter combinations
- [ ] No new dependencies added (use built-in `json` module)

---

## Constraints

- Do not change the default table output format
- Do not add new dependencies
- Keep changes within `src/commands/list.py`, `tests/commands/test_list.py`, and docs

---

## Context

- `src/commands/list.py` — current list command implementation
- `tests/commands/test_list.py` — existing tests for list command
- `docs/commands.md` — needs updating with JSON flag documentation

---

## Expected Output

- Modified `src/commands/list.py` with `--json` flag
- Updated `tests/commands/test_list.py` with JSON tests
- Updated `docs/commands.md`

---

## Out of Scope

- CSV output (separate task, #23)
- XML output (not requested)
- Pretty-printed JSON with colours (keep it raw for piping)

---

## Time Estimate

- Expected: 1–2 hours
- Hard stop: Stop after 3 hours and hand off regardless of progress

---

## Notes

- Focus on tests first — red-green-refactor
- The existing `Task.to_dict()` method should make JSON serialization trivial
