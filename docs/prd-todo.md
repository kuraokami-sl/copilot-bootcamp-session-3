# Product Requirements Document (PRD) - Todo App Upgrade

## 1. Overview

We are upgrading the basic Todo app so users can organize tasks with due dates, priorities, and date-based filters while keeping the MVP simple and teachable. The current app is intentionally basic, and the requested upgrade should make tasks easier to triage without introducing backend changes, external storage, or advanced workflow features.

The MVP focuses on adding the task data and views needed to answer: what is due today, what is overdue, and how important is each task?

---

## 2. MVP Scope

- Add an optional `dueDate` field to each task.
- Store `dueDate` values in ISO `YYYY-MM-DD` format.
- Treat invalid `dueDate` values as absent.
- Add a `priority` field to each task.
- Support priority values `P1`, `P2`, and `P3`.
- Default new tasks to priority `P3` when no priority is provided.
- Require every task to have a `title`.
- Add task filters for `All`, `Today`, and `Overdue`.
- Show completed tasks in the `All` filter.
- Hide completed tasks from the `Today` and `Overdue` filters.
- Keep task storage local.
- Avoid backend changes and external storage for the MVP.

---

## 3. Post-MVP Scope

- Visually highlight overdue tasks so they stand out from non-overdue tasks.
- Use red visual treatment for overdue tasks if a color treatment is added.
- Add visual priority badges.
- Use red for `P1`, orange for `P2`, and gray for `P3` if priority badge colors are added.
- Add task sorting with the following order:
  - Overdue tasks first.
  - Then priority from `P1` to `P3`.
  - Then due date ascending.
  - Then tasks without due dates last.

---

## 4. Out of Scope

- Notifications.
- Recurring tasks.
- Multi-user functionality.
- Keyboard navigation enhancements.
- Special accessibility features beyond the existing app baseline.
- Backend changes.
- External storage.
