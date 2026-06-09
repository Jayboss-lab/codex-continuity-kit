# Handoff Update Checklist

Use this checklist when updating a `CODEX_HANDOFF.md` file to make sure it's actually useful to the next person or agent reading it.

---

## Structure checks

- [ ] Session metadata filled (date, agent, user, project)
- [ ] Summary is 2–4 sentences and captures the essence
- [ ] "What Was Explored" lists actual files or areas, not vague descriptions
- [ ] "Decisions Made" is not empty — even "no decision" is worth noting
- [ ] "Code Changes" table links files to specific changes
- [ ] "Next Steps" is ordered by priority and specific enough to act on
- [ ] "Context for Next Session" is the first thing the next reader sees and is genuinely useful

## Clarity checks

- [ ] No internal codenames or private project references
- [ ] No unexplained abbreviations
- [ ] File paths are relative and accurate
- [ ] Blockers are specific ("Need OAuth client ID" > "Something is blocked")
- [ ] Next steps mention prerequisites if there are any ("Do X after Y is available")

## Completeness checks

- [ ] If tests were run, results are noted
- [ ] If work is incomplete, the boundary is clear ("Implemented route handler but not tests")
- [ ] If work depends on another task, that task is referenced
- [ ] If there are risks or warnings, they are flagged
- [ ] Notes section captures observations that don't fit elsewhere (dead ends, ideas, surprises)

## Honesty checks

- [ ] I did not pretend something is done when it's only started
- [ ] I did not omit failures or dead ends because they're embarrassing
- [ ] I noted when I was guessing or uncertain about something
- [ ] I admitted when scope crept or priorities shifted mid-session

---

## Example of a bad handoff vs. a good handoff

### Bad

> Fixed auth stuff. Will do OAuth next.

### Good

> Explored current auth module. Decided to use Authlib for OAuth instead of custom client (see AGENTS.md for rationale). Added OAuth environment variables to config but did not implement routes yet — waiting on client credentials.
> Next: implement /oauth/login and /oauth/callback routes once credentials are available.
