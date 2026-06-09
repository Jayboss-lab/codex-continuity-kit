# Safe Codex Session Checklist

Use this checklist before starting a Codex (or other AI coding agent) session. It prevents common accidents: wrong files touched, tests skipped, credentials leaked.

---

## Pre-flight checks

- [ ] I have read `AGENTS.md` (if it exists in this repo)
- [ ] I have read the latest `CODEX_HANDOFF.md` to understand current state
- [ ] I know the scope of this session and have a structured goal
- [ ] I am on the correct branch (not `main` unless intentionally fixing something small)
- [ ] My working directory is clean or I know what's uncommitted

## During the session

- [ ] I review every file change before accepting it
- [ ] I run tests before claiming completion
- [ ] I do not paste API keys, passwords, or tokens into the agent prompt
- [ ] I keep session scope tight — one goal per session if possible
- [ ] I update `CODEX_HANDOFF.md` as I go if decisions change

## Before ending the session

- [ ] All intended changes are committed or explicitly documented as drafts
- [ ] `CODEX_HANDOFF.md` is updated with:
  - What was explored
  - What decisions were made
  - What changed
  - What's next
  - Any blockers or open questions
- [ ] No temporary files, debug logs, or `.env` files are staged for commit
- [ ] I run `git diff --cached` to review what's going out
- [ ] Tests pass (or failures are documented in the handoff)

## After the session

- [ ] I commit the handoff file
- [ ] I push the branch (or note that it needs pushing)
- [ ] I close or save the terminal session gracefully
