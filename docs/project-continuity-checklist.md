# Project Continuity Checklist

Use this checklist when returning to a project after days, weeks, or when picking up a project you didn't start. It ensures you don't miss critical context.

---

## Before resuming work

- [ ] Read the latest `CODEX_HANDOFF.md` (or equivalent continuity file)
- [ ] Check `AGENTS.md` for updated conventions
- [ ] Review recent commits: `git log --oneline -20`
- [ ] Check open issues or tasks in your project's tracker
- [ ] Verify environment still works: run setup steps in `AGENTS.md`

## If there is no handoff file

- [ ] Check `README.md` for project overview
- [ ] Review the directory structure — has it changed significantly?
- [ ] Look at recent git diffs to understand what was last worked on
- [ ] Search for TODO or FIXME comments in the codebase
- [ ] Check for any `POST_RUN_REPORT.md` files from previous milestones

## While catching up

- [ ] Update or create a `CODEX_HANDOFF.md` with what you learn
- [ ] Note any surprises (e.g. "I thought this was done but it's not")
- [ ] Document any assumptions you're making to proceed

## Before starting new work

- [ ] Write a `GOAL_PROMPT.md` for the new task
- [ ] Confirm the goal doesn't overlap with or conflict with existing priorities
- [ ] Check if the goal is still relevant (priorities may have shifted)
