# Service Brief: Launch List

## Summary

Launch List is a lightweight service for founders who need to track launch tasks before releasing a small product. It helps a founder collect tasks, group them by launch area, and see what is still blocking launch.

## Why

Founders often keep launch tasks scattered across notes, chat, and spreadsheets. The service should make the launch plan visible enough that a founder can decide what to do next and what is blocking release.

## Users

- Founder: creates and manages the launch checklist.
- Collaborator: views tasks and updates task status.

## Core Functions

- Manage launch tasks: create, edit, complete, and delete tasks.
- Group tasks by area: organize tasks into product, marketing, legal, operations, and technical areas.
- Track blockers: mark tasks as blocked and explain why.
- Show launch readiness: summarize completed, pending, and blocked tasks.

## Pages / Screens

- Dashboard: overview of launch readiness, blocked tasks, and upcoming work.
- Task List: grouped list of launch tasks with filters by status and area.
- Task Detail: task description, owner, status, blocker notes, and activity.
- Settings: manage collaborators and launch areas.

## Entities

- User: a person who can access the service.
  - fields: name, email, role
  - relationships: owns many Launches, can be assigned Tasks
- Launch: a product launch plan.
  - fields: name, target date, status
  - relationships: has many Tasks, has many Launch Areas
- Task: a launch action item.
  - fields: title, description, status, due date, blocker note
  - relationships: belongs to Launch, belongs to Launch Area, assigned to User
- Launch Area: a category for launch work.
  - fields: name, description
  - relationships: belongs to Launch, has many Tasks

## Unknowns

- Should collaborators need accounts, or can they access by invite link?
- Should v1 support multiple launches per founder?
- Should task activity history be included in v1?
- Should launch readiness be a simple percentage or a richer scoring model?

## User Flows

### Create a launch plan

1. Founder creates a launch with a name and target date.
2. System creates default launch areas.
3. Founder adds tasks to each area.
4. System shows launch readiness on the dashboard.

### Mark a task as blocked

1. Founder opens a task.
2. Founder changes the task status to blocked and writes a blocker note.
3. System highlights the task on the dashboard.

### Invite a collaborator

1. Founder opens settings.
2. Founder invites a collaborator by email.
3. System gives the collaborator access to the launch.

## Business Rules

- A task can be pending, completed, or blocked.
- Blocked tasks must include a blocker note.
- Launch readiness should not count blocked tasks as ready.
- Only founders can invite collaborators.

## Integrations

- Email delivery: send collaborator invitations.

## Auth / Permissions

- Founder: can manage launches, tasks, launch areas, and collaborators.
- Collaborator: can view launches and update assigned tasks.

## Constraints

- The first version should be simple enough for one founder to use without setup help.
- Mobile web should be usable, but native mobile apps are not required.
- The service should not generate production code from this brief.

## Non-Functional Requirements

- Accessibility: keyboard access and readable contrast for task workflows.
- Reliability: task updates should not be lost.
- Privacy: launch plans should not be public by default.

## Success Metrics

- A founder can create a launch and add first tasks within five minutes.
- A founder can identify blocked tasks from the dashboard.

## Risks

- If the readiness score is too abstract, users may not trust it.
- If collaboration requires too much setup, founders may avoid inviting others.

## Notes

This example is intentionally small. It should be enough for TDS to generate PRD, ERD, API, page-flow, design, architecture, implementation, and questions docs without needing production code generation.
