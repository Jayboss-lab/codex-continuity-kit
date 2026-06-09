# AGENTS.md

**Project:** Aurelia UI Component Library  
**Last updated:** 2026-03-15  
**Maintainer:** Sam Rivera

---

## Project Overview

A React component library for data-dense dashboards. Focused on tables, charts, filters, and navigation patterns. Used by internal products and planned for public release.

**Tech stack:** React 18 + TypeScript + Tailwind CSS + Storybook + Vitest  
**Primary languages:** TypeScript, CSS  
**Entry points:** `src/index.ts` (public API), `src/components/` (individual exports)  
**Test command:** `npm test` (Vitest)

---

## Agent Behaviour Rules

### Do
- [ ] Read component design guidelines in `docs/design-system.md` before creating new components
- [ ] Write stories for every new component in Storybook
- [ ] Run visual regression tests (`npm run test:visual`) before claiming completion
- [ ] Update `CODEX_HANDOFF.md` after each session
- [ ] Follow the existing component API patterns (composition over configuration)

### Don't
- [ ] Introduce new dependencies without discussion
- [ ] Break existing component APIs without a migration plan
- [ ] Skip accessibility checks (axe-core runs in CI)
- [ ] Use inline styles — Tailwind classes only

---

## Project Conventions

### Directory structure

```
aurelia-ui/
  src/
    components/          — React components (one folder per component)
    hooks/               — Shared hooks
    utils/               — Pure utility functions
    types/               — Shared TypeScript types
  stories/               — Storybook stories
  tests/                 — Vitest test files
  docs/                  — Design system docs
```

### Component structure
Each component lives in `src/components/ComponentName/`:
```
ComponentName/
  index.tsx             — Main component
  types.ts              — Component-specific types
  utils.ts              — Helper functions
  ComponentName.test.tsx — Tests
  ComponentName.stories.tsx — Storybook stories
```

### API conventions
- Props named with clear intent: `isLoading`, `onSort`, `variant`, `size`
- `variant` values come from design tokens: `primary`, `secondary`, `ghost`, `danger`
- Forward refs where appropriate for library consumers

### Key dependencies
- `react` + `react-dom` — UI framework
- `tailwindcss` — Styling
- `@storybook/react` — Component documentation
- `vitest` + `@testing-library/react` — Testing
- `axe-core` — Accessibility validation

### Environment setup

```bash
npm install
npm run storybook   # Start Storybook for development
npm test            # Run unit tests
npm run test:visual # Run visual regression tests
```

---

## Context Files

- `README.md` — Library overview and usage
- `CODEX_HANDOFF.md` — Current session state
- `docs/design-system.md` — Design tokens, colour palette, spacing scale
- `docs/component-api-guide.md` — How to design component APIs in this library

---

## Current Priorities

1. Add `DataTable` component with sorting and pagination
2. Fix `FilterBar` accessibility issues (screen reader announcements)
3. Create migration guide for v2 → v3 (breaking changes in `Chart` component)

---

## Known Issues

- `Chart` component tooltip positioning breaks on mobile viewports
- `FilterBar` dropdown does not trap focus (a11y fail)
- Some stories use mock data that references internal product names

## Recent Decisions

- Switched from Jest to Vitest for faster test runs
- Using CSS variables for design tokens instead of Tailwind config extension
- `DataTable` will use headless `@tanstack/react-table` for logic, custom styling via Tailwind
