# GOAL_PROMPT.md

**Date:** `[YYYY-MM-DD]`  
**Project:** `[PROJECT_NAME]`  
**Session:** `[SESSION_NUMBER]`  
**Priority:** `[CRITICAL / HIGH / MEDIUM / LOW]`

---

## Goal

A single clear sentence describing what the agent should accomplish.

**Example:** *"Implement password reset functionality: token generation, email dispatch, token validation, and password update endpoint."*

---

## Background

Why this goal matters and what came before it. Keep it brief — 2–4 sentences max.

**Example:** *"Users currently have no way to recover forgotten passwords. This blocks sign-ups from security-conscious users. The email service is already configured (see src/services/email.py)."*

---

## Acceptance Criteria

Specific, testable criteria for when this goal is complete.

- [ ] `[Criterion 1: e.g. /api/auth/forgot-password accepts email and returns 202 Accepted]`
- [ ] `[Criterion 2: e.g. Reset token expires after 1 hour]`
- [ ] `[Criterion 3: e.g. /api/auth/reset-password validates token and updates password]`
- [ ] `[Criterion 4: e.g. Both endpoints have integration tests]`
- [ ] `[Criterion 5: e.g. Error cases handled: invalid token, expired token, unknown email]`

---

## Constraints

What the agent should respect while working.

- `[Constraint 1: e.g. Do not use external email services — use existing internal email sender]`
- `[Constraint 2: e.g. Must work with existing PostgreSQL schema — no new tables]`
- `[Constraint 3: e.g. Keep changes within src/auth/ and tests/auth/ unless absolutely necessary]`

---

## Context

Files, docs, or previous handoffs the agent should read before starting.

- `CODEX_HANDOFF.md` — current session state
- `AGENTS.md` — project conventions
- `[File/link 1: e.g. src/auth/models.py — user table schema]`
- `[File/link 2: e.g. docs/auth.md — existing auth flow documentation]`

---

## Expected Output

What should exist when the goal is achieved.

- `[File 1: e.g. src/auth/password_reset.py]`
- `[File 2: e.g. tests/auth/test_password_reset.py]`
- `[Documentation update: e.g. Update API docs with new endpoints]`

---

## Out of Scope

What this goal explicitly does NOT include.

- `[e.g. Frontend password reset form — that's a separate task]`
- `[e.g. Rate limiting on password reset — will be handled in #44]`
- `[e.g. OAuth integration — unrelated to this flow]`

---

## Time Estimate

How long this should take. If the agent is running out of time, they should update the handoff and stop.

- **Expected:** `[e.g. 1–2 hours]`
- **Hard stop:** `[e.g. Stop after 3 hours and hand off regardless of progress]`

---

## Notes

- `[Any special instructions: e.g. "Focus on tests first — red-green-refactor pattern"]`
- `[Known risks: e.g. "The email service occasionally times out in tests — use mock if needed"]`
