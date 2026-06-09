# GOAL_PROMPT.md

**Date:** 2026-03-14  
**Project:** Aurelia UI Component Library  
**Session:** 23  
**Priority:** HIGH

---

## Goal

Implement a `DataTable` component with client-side sorting, pagination, and row selection. Must match existing design tokens and follow component API conventions.

---

## Background

The library lacks a data table component. Product teams are using ad-hoc table implementations. A library-standard component will reduce duplication and ensure consistency. The `@tanstack/react-table` library is approved for internal use.

---

## Acceptance Criteria

- [ ] `DataTable` component accepts column definitions and row data
- [ ] Sorting by column header click (single-column sort, toggle asc/desc)
- [ ] Pagination with compact variant (5 visible page buttons)
- [ ] Row selection via checkboxes with select-all header checkbox
- [ ] 8 Storybook stories covering: default, sorting, pagination, selection, empty state, loading, compact variant, full variant
- [ ] 12 unit tests covering sort, pagination, selection, and edge cases
- [ ] Follows existing component directory structure and naming conventions
- [ ] No new runtime dependencies beyond `@tanstack/react-table` and `lucide-react` (already approved)

---

## Constraints

- Use `@tanstack/react-table` for table logic — do not build table state management from scratch
- Use Tailwind for styling — no inline styles, no CSS-in-JS
- Design tokens from `docs/design-system.md` must be used (row heights, colours, spacing)
- Component API should accept `columns` and `data` props, similar to `tanstack` conventions
- Must be accessible: keyboard navigation, ARIA labels, focus management

---

## Context

- `src/components/` — existing component structure (see `Button/` for pattern)
- `docs/design-system.md` — design tokens and spacing scale
- `docs/component-api-guide.md` — how to structure component APIs
- `src/hooks/` — existing hooks (may need `useFocusTrap`)

---

## Expected Output

- `src/components/DataTable/index.tsx`
- `src/components/DataTable/types.ts`
- `src/components/DataTable/DataTable.test.tsx`
- `src/components/DataTable/DataTable.stories.tsx`
- Updated `docs/design-system.md` (if new tokens needed)

---

## Out of Scope

- Server-side sorting/pagination (client-side only for v1)
- Virtualised rows for large datasets
- Column resizing or reordering
- Export to CSV/Excel

---

## Time Estimate

- Expected: 3–4 hours
- Hard stop: Stop after 5 hours and hand off. Component should be testable even if not polished.

---

## Notes

- Focus on getting `@tanstack/react-table` wired up with the library's styling first. Polish comes after basic functionality works.
- The existing `Button` and `Checkbox` components should be reused for table controls.
- Sort icons from `lucide-react`: `ArrowUpDown`, `ArrowUp`, `ArrowDown`.
