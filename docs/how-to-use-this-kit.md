# How to Use This Kit

A step-by-step adoption guide for individuals and teams.

---

## For a solo developer

### 1. Copy the templates you need

Pick the templates relevant to your workflow. Most people start with:

- `AGENTS.md` — define how your agent should behave in this repo
- `CODEX_HANDOFF.md` — track session state

Copy them from [`templates/`](../templates/) into your project root.

### 2. Rename them

Remove `.template` from the filename:

```bash
mv AGENTS.template.md AGENTS.md
mv CODEX_HANDOFF.template.md CODEX_HANDOFF.md
```

### 3. Fill in the placeholders

Replace everything in `[square brackets]` with real information. Be specific.

### 4. Commit them

```bash
git add AGENTS.md CODEX_HANDOFF.md
git commit -m "docs: add agent context templates"
```

These are project documentation. They belong in version control.

### 5. Use them

Before each session: read `AGENTS.md`.  
After each session: update `CODEX_HANDOFF.md`.  
Next session: read `CODEX_HANDOFF.md` first.

---

## For a team

### 1. Agree on conventions

Pick a subset of templates the whole team will use. Not everyone needs every template.

| Team size | Recommended minimum |
|---|---|
| Solo | `AGENTS.md`, `CODEX_HANDOFF.md` |
| 2–3 devs | Above + `POST_RUN_REPORT.md` for milestones |
| 4+ devs | Above + `SKILL.md` for repeatable patterns |
| Multi-project | `GOAL_PROMPT.md` for external contributors |

### 2. Create a team template repo

If you have multiple projects, create a private repo with your team's filled-in `AGENTS.md` as a starting point. New projects clone it and customise.

### 3. Establish a handoff ritual

At the end of each session, the developer updates the handoff file. If they cannot (e.g. session crashed), they write it from memory as soon as possible.

The next developer reads it before starting. No exceptions.

### 4. Review handoffs in standup

If you do daily standups, read the latest handoff update. It replaces "what did you do yesterday?" with "what does the next person need to know?"

---

## How this works with Codex CLI

Codex CLI is the primary target for these templates. Here's how to use them effectively:

### Before starting Codex

1. Ensure `AGENTS.md` and `CODEX_HANDOFF.md` exist in the repo
2. Copy the relevant sections into your initial prompt or reference them with file paths:
   ```
   Read CODEX_HANDOFF.md before proceeding.
   ```

### While in session

- Codex can read markdown files. Point it at your templates.
- Ask Codex to update the handoff as it works: *"Update CODEX_HANDOFF.md with what we just decided."*

### After session

- Review the handoff Codex wrote. Fix anything unclear.
- Commit it alongside your code changes.

---

## How this works with Claude Code

Claude Code has slightly different conventions:

- Use `CLAUDE.md` instead of `AGENTS.md` if you want native Claude Code support (Claude reads `CLAUDE.md` automatically)
- The `CODEX_HANDOFF.md` template still works; rename it to `CLAUDE_HANDOFF.md` if you prefer
- Claude Code has a `/memory` feature but it does not persist across sessions — handoff files still matter

---

## How this works with Aider

Aider has built-in support for `.aider.conf.yml` and context files:

- You can include `AGENTS.md` in Aider's context using `--read AGENTS.md`
- Aider's `/clipboard` and `/paste` features make it easy to pass handoff content
- Consider using Aider's "architect" mode for complex tasks and recording the architecture decisions in `POST_RUN_REPORT.md`

---

## Troubleshooting

### "I keep forgetting to update the handoff"

Set a terminal alias or a pre-exit script that prompts you:

```bash
# In your .bashrc or .zshrc
alias codex-done='echo "Did you update CODEX_HANDOFF.md? (y/n)"; read ans; [ "$ans" = "y" ] || echo "Do it now."'
```

### "The handoff is getting too long"

Archive old handoffs:

```bash
mv CODEX_HANDOFF.md handoffs/CODEX_HANDOFF_2026-01-15.md
```

Create a new `CODEX_HANDOFF.md` for the current session. Link to the archive in the new file.

### "My team thinks this is bureaucratic"

Start with just `CODEX_HANDOFF.md`. Use it for one week. If it saves time, add more templates. If it doesn't, simplify or discard.

This kit is a tool, not a mandate.

---

## Advanced: linking templates together

For complex projects, templates can reference each other:

- `GOAL_PROMPT.md` → references `AGENTS.md` for constraints
- `CODEX_HANDOFF.md` → references `POST_RUN_REPORT.md` for milestone summaries
- `SKILL.md` → referenced by `GOAL_PROMPT.md` when the goal uses a known pattern

This creates a lightweight documentation web without heavyweight tools.
