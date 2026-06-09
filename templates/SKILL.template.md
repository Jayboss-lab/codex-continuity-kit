# SKILL.md

**Skill name:** `[SKILL_NAME]`  
**Version:** `1.0.0`  
**Last updated:** `[YYYY-MM-DD]`  
**Project:** `[PROJECT_NAME]`

---

## What this skill does

A one-paragraph description of what this skill enables the agent to do. This should be a repeatable task pattern, not a one-off task.

**Example:** *"Generate a new API endpoint with standard boilerplate: route handler, request validation, response schema, and a basic integration test."*

---

## When to use this skill

- `[Situation 1: e.g. "When adding a new REST endpoint to the public API"]`
- `[Situation 2: e.g. "When creating a new database migration with rollback support"]`

## When NOT to use this skill

- `[Anti-pattern 1: e.g. "Don't use this for internal-only admin endpoints — those have different auth requirements"]`
- `[Anti-pattern 2: e.g. "Don't skip the integration test step"]`

---

## Prerequisites

What must be true before this skill can be used:

- `[e.g. Database schema must be up to date]`
- `[e.g. User must have run npm install]`
- `[e.g. The config file at config/api.yml must exist]`

---

## Steps

### Step 1: `[Name]`
What to do and how.

**Expected inputs:** `[what the agent needs from the user]`  
**Expected outputs:** `[what files or changes should result]`

### Step 2: `[Name]`
What to do and how.

**Validation:** `[how to verify this step succeeded]`

### Step 3: `[Name]`
...

---

## Output format

When completing this skill, the agent should produce:

- `[File 1: e.g. src/routes/{name}.py — route handler]`
- `[File 2: e.g. tests/routes/test_{name}.py — integration test]`
- `[Documentation update if applicable]`

---

## Error handling

If something goes wrong during this skill:

1. `[e.g. Stop and report the error in the handoff]`
2. `[e.g. Do not commit broken code to main]`
3. `[e.g. Rollback any partial changes unless instructed otherwise]`

---

## Examples

### Example 1: `[Scenario name]`
**Input:** `[what the user asked for]`  
**Process:** `[what the agent did]`  
**Result:** `[what files were created/modified]`

### Example 2: `[Scenario name]`
**Input:** `[...]`  
**Process:** `[...]`  
**Result:** `[...]`

---

## Related skills

- `[SKILL_NAME_2]` — `[how it relates]`
- `[SKILL_NAME_3]` — `[how it relates]`
