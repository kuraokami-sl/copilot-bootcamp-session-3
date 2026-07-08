# MVP Epics

- Epic: Task Due Dates
	- Criteria: Tasks can include an optional `dueDate` field.
	- Criteria: `dueDate` values use ISO `YYYY-MM-DD` format.
	- Criteria: Tasks without a due date remain valid.
- Epic: Task Priority Levels
	- Criteria: Tasks can include a `priority` field.
	- Criteria: Supported priority values are `P1`, `P2`, and `P3`.
	- Criteria: New tasks default to `P3` when no priority is provided.
- Epic: Date-Based Task Filters
	- Criteria: Users can filter tasks by `All`, `Today`, and `Overdue`.
	- Criteria: The `All` filter includes completed and incomplete tasks.
	- Criteria: The `Today` and `Overdue` filters show only incomplete tasks.
- Epic: Local Task Data Validation
	- Criteria: Every task requires a `title`.
	- Criteria: Invalid `dueDate` values are treated as absent.
	- Criteria: Priority values are limited to `P1`, `P2`, and `P3`.
- Epic: Local-Only Task Storage
	- Criteria: Task data remains in local storage.
	- Criteria: The MVP does not require backend changes.
	- Criteria: The MVP does not use external storage.

# Post-MVP Epics

- Epic: Overdue Task Highlighting
	- Criteria: Overdue tasks are visually distinguishable from non-overdue tasks.
	- Criteria: A red visual treatment is used for overdue tasks if color is applied.
- Epic: Priority Badge Styling
	- Criteria: Tasks display visual priority badges.
	- Criteria: `P1` badges use red if color is applied.
	- Criteria: `P2` badges use orange if color is applied.
	- Criteria: `P3` badges use gray if color is applied.
- Epic: Task Sorting
	- Criteria: Overdue tasks appear first.
	- Criteria: Tasks are sorted by priority from `P1` to `P3` after overdue status.
	- Criteria: Tasks are sorted by due date ascending after priority.
	- Criteria: Tasks without due dates appear last.

# Technical Requirements

- Requirement: Implement MVP changes in the frontend without backend API changes.
- Requirement: Persist task updates in local storage only.
- Requirement: Represent `dueDate` as an optional ISO `YYYY-MM-DD` string.
- Requirement: Treat missing or invalid `dueDate` values as no due date.
- Requirement: Represent `priority` as one of `P1`, `P2`, or `P3`.
- Requirement: Default missing priority values to `P3`.
- Requirement: Preserve existing task completion behavior.
- Requirement: Keep `All`, `Today`, and `Overdue` filter logic deterministic and testable.
- Requirement: Add tests for due date handling, priority defaults, validation, and filters.
- Requirement: Follow existing JavaScript and React coding conventions.
