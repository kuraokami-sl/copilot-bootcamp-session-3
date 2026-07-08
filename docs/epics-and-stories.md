# MVP Epics

- Epic: Task Due Dates
	- Story: Add due date field to tasks
	- Story: Save due dates in ISO format
	- Story: Allow tasks without due dates
	- Acceptance Criteria:
		- Tasks can include an optional `dueDate` field.
		- `dueDate` values use ISO `YYYY-MM-DD` format.
		- Tasks without a due date remain valid.

- Epic: Task Priority Levels
	- Story: Add priority field to tasks
	- Story: Support P1 P2 P3 priorities
	- Story: Default new tasks to P3
	- Acceptance Criteria:
		- Tasks can include a `priority` field.
		- Supported priority values are `P1`, `P2`, and `P3`.
		- New tasks default to `P3` when no priority is provided.

- Epic: Date-Based Task Filters
	- Story: Add All tasks filter
	- Story: Add Today tasks filter
	- Story: Add Overdue tasks filter
	- Story: Hide completed tasks in date filters
	- Acceptance Criteria:
		- Users can filter tasks by `All`, `Today`, and `Overdue`.
		- The `All` filter includes completed and incomplete tasks.
		- The `Today` and `Overdue` filters show only incomplete tasks.

- Epic: Local Task Data Validation
	- Story: Require task titles
	- Story: Ignore invalid due dates
	- Story: Restrict priority values
	- Acceptance Criteria:
		- Every task requires a `title`.
		- Invalid `dueDate` values are treated as absent.
		- Priority values are limited to `P1`, `P2`, and `P3`.

- Epic: Local-Only Task Storage
	- Story: Persist task changes locally
	- Story: Keep MVP frontend only
	- Story: Avoid external storage integration
	- Acceptance Criteria:
		- Task data remains in local storage.
		- The MVP does not require backend changes.
		- The MVP does not use external storage.

# Post-MVP Epics

- Epic: Overdue Task Highlighting
	- Story: Highlight overdue tasks visually
	- Story: Apply red overdue styling
	- Acceptance Criteria:
		- Overdue tasks are visually distinguishable from non-overdue tasks.
		- A red visual treatment is used for overdue tasks if color is applied.

- Epic: Priority Badge Styling
	- Story: Display priority badges on tasks
	- Story: Apply P1 badge styling
	- Story: Apply P2 badge styling
	- Story: Apply P3 badge styling
	- Acceptance Criteria:
		- Tasks display visual priority badges.
		- `P1` badges use red if color is applied.
		- `P2` badges use orange if color is applied.
		- `P3` badges use gray if color is applied.

- Epic: Task Sorting
	- Story: Sort overdue tasks first
	- Story: Sort tasks by priority
	- Story: Sort tasks by due date
	- Story: Place undated tasks last
	- Acceptance Criteria:
		- Overdue tasks appear first.
		- Tasks are sorted by priority from `P1` to `P3` after overdue status.
		- Tasks are sorted by due date ascending after priority.
		- Tasks without due dates appear last.

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
