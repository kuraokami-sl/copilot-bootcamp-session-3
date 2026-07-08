# Cloud Architecture Overview

## System Context

The Todo app is a JavaScript monorepo with a React frontend and a Node.js/Express API. The frontend sends task requests to the Express API, and the API stores task data in memory for the current runtime. No external database or cloud storage service is required for the current scope.

```mermaid
flowchart LR
  user[User]
  browser[Web Browser]
  frontend[React Todo App]
  api[Express API]
  memory[(In-Memory Storage)]

  user --> browser
  browser --> frontend
  frontend --> api
  api --> memory
```

## Create TODO Sequence

```mermaid
sequenceDiagram
  actor User
  participant Frontend as React Todo App
  participant API as Express API
  participant Store as In-Memory Storage

  User->>Frontend: Enter TODO details
  User->>Frontend: Submit create TODO form
  Frontend->>Frontend: Validate title, due date, and priority
  Frontend->>API: POST /tasks
  API->>API: Validate request payload
  API->>Store: Save TODO in memory
  Store-->>API: Return saved TODO
  API-->>Frontend: Respond with created TODO
  Frontend-->>User: Show TODO in task list
```

## MVP Context

- Users interact with the Todo app through the React frontend.
- The React frontend communicates with the Express API for task operations.
- The Express API stores task data in memory.
- Due dates, priorities, filters, and validation are supported by the application flow.
- Data resets when the API process restarts because storage is in memory.
- No external storage, authentication, notifications, recurring jobs, or multi-user services are included.

## Deployment Context

- The frontend can be hosted as a static web application.
- The Express API can be deployed as a lightweight Node.js service.
- In-memory storage keeps the deployment simple but is not durable across restarts.