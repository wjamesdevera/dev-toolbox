# Software Engineering Workflow Guide

A lightweight workflow for managing software projects from idea to delivery.

This guide is designed for **solo developers and freelancers**, but the workflow can also scale when collaborators are added.

The goal is not to create a complicated process.

The goal is to consistently move a project from:

```text
Idea
  ↓
Plan
  ↓
Build
  ↓
Test
  ↓
Review
  ↓
Release
  ↓
Maintain
```

---

# Table of Contents

1. [The Overall Workflow](#1-the-overall-workflow)
2. [Project Documentation](#2-project-documentation)
   - [Project Brief](#project-brief)
   - [Requirements](#requirements)
   - [Project Plan](#project-plan)
   - [Decision Log](#decision-log)
3. [Define the MVP](#3-define-the-mvp)
4. [Create the Backlog](#4-create-the-backlog)
5. [Use Trello to Manage Work](#5-use-trello-to-manage-work)
6. [Create a Good Task](#6-create-a-good-task)
7. [Define "Done"](#7-define-done)
8. [Start Development](#8-start-development)
9. [Development Workflow](#9-development-workflow)
10. [Research and Learning](#10-research-and-learning)
11. [Handling Blockers](#11-handling-blockers)
12. [Handling Bugs](#12-handling-bugs)
13. [Keep Work in Progress Small](#13-keep-work-in-progress-small)
14. [Commit Your Work](#14-commit-your-work)
15. [Code Review](#15-code-review)
16. [Testing](#16-testing)
17. [Move to Review / Testing](#17-move-to-review--testing)
18. [Definition of Done](#18-definition-of-done)
19. [Release Planning](#19-release-planning)
20. [Client Projects](#20-client-projects)
21. [Handling Client Change Requests](#21-handling-client-change-requests)
22. [Client Progress Updates](#22-client-progress-updates)
23. [Release Workflow for Freelance Projects](#23-release-workflow-for-freelance-projects)
24. [Deployment](#24-deployment)
25. [Post-Release](#25-post-release)
26. [Project Maintenance](#26-project-maintenance)
27. [When the Project Grows](#27-when-the-project-grows)
28. [Recommended Tools](#28-recommended-tools)
29. [The Relationship Between Your Tools](#29-the-relationship-between-your-tools)
30. [The Complete Daily Workflow](#30-the-complete-daily-workflow)
31. [The Complete Project Workflow](#31-the-complete-project-workflow)
32. [The Rules](#32-the-rules)
33. [Minimal Workflow](#33-minimal-workflow)

---

# 1. The Overall Workflow

Use this as the project's overall lifecycle:

```text
1. Define
   ↓
2. Plan
   ↓
3. Break Down
   ↓
4. Develop
   ↓
5. Test
   ↓
6. Review
   ↓
7. Release
   ↓
8. Maintain
```

Each stage answers a different question.

| Stage      | Question                      |
| ---------- | ----------------------------- |
| Define     | What are we building and why? |
| Plan       | What is the approach?         |
| Break Down | What work needs to be done?   |
| Develop    | How do we implement it?       |
| Test       | Does it work correctly?       |
| Review     | Is it good enough to ship?    |
| Release    | How do we get it to users?    |
| Maintain   | What happens after release?   |

---

# 2. Project Documentation

Before creating development tasks, establish the project's basic documentation.

For a small project:

```text
project/
├── README.md
│
├── docs/
│   ├── project-brief.md
│   ├── requirements.md
│   ├── project-plan.md
│   └── decisions.md
│
└── src/
```

## Project Brief

Answers:

> What are we building and why?

Contains:

- Problem
- Goal
- Target users
- Core features
- Success criteria
- Technology
- Out of scope

---

## Requirements

Answers:

> What should the software do?

Contains:

- Functional requirements
- Acceptance criteria
- Important non-functional requirements
- Out-of-scope features

---

## Project Plan

Answers:

> How are we going to get this done?

Contains:

- Milestones
- Major phases
- Dependencies
- Target dates
- Current status

---

## Decision Log

Answers:

> Why did we choose this approach?

Record important decisions such as:

- Technology choices
- Architecture decisions
- Scope changes
- Client decisions
- Important tradeoffs

Do not record every tiny decision.

---

# 3. Define the MVP

Before creating a large backlog, define the smallest useful version of the product.

Ask:

> What is the minimum version that solves the original problem?

Example:

### Developer Daily Log

MVP:

```text
Create a daily log
        ↓
Save the log
        ↓
View previous logs
```

Not:

```text
AI summaries
Analytics
Gamification
Notifications
Social sharing
Advanced filtering
```

Those can come later.

---

# 4. Create the Backlog

Once the MVP is defined, turn requirements into potential work.

Example:

```text
Backlog

- Create database
- Create Log model
- Create log API
- Create log form
- Connect form to API
- Display previous logs
- Add validation
- Add empty state
- Add authentication
```

The backlog is **not a commitment**.

It is a pool of potential work.

New ideas should normally go into the backlog instead of interrupting the current task.

---

# 5. Use Trello to Manage Work

Trello is used for **execution**, not for storing the entire project's knowledge.

Recommended board:

```text
Backlog
    ↓
Ready
    ↓
In Progress
    ↓
Review / Testing
    ↓
Done
```

### Backlog

Potential future work.

### Ready

Work that is clearly defined and ready to start.

### In Progress

Work currently being implemented.

### Review / Testing

Implementation is finished but still needs verification.

### Done

The work has been verified and completed.

---

# 6. Create a Good Task

A task should represent **meaningful engineering work**.

Good:

```text
Create Log model
Create POST /logs endpoint
Create log submission form
Display previous logs
Add validation to log form
```

Bad:

```text
Work on frontend
Fix backend
Build application
Make UI better
```

A task should answer:

> What am I actually going to accomplish?

---

# 7. Define "Done"

Before starting a task, know what completion means.

Example:

```markdown
## Done When

- [ ] User can submit a log
- [ ] Log is saved to the database
- [ ] Invalid input is rejected
- [ ] Success state is displayed
- [ ] Feature has been manually tested
```

This prevents:

> "I think I'm finished?"

from becoming a recurring problem.

---

# 8. Start Development

When you start a task:

```text
Ready
  ↓
In Progress
```

Create an appropriate Git branch.

Example:

```text
feature/create-log-endpoint
```

Then:

```text
Trello Task
     ↓
Git Branch
     ↓
Implementation
     ↓
Commit
```

---

# 9. Development Workflow

While implementing a task:

```text
Understand task
      ↓
Inspect existing code
      ↓
Plan implementation
      ↓
Implement
      ↓
Run locally
      ↓
Test
      ↓
Commit
```

Don't immediately start coding if you don't understand what you're building.

Spend a few minutes identifying:

- Existing code involved
- Dependencies
- Expected behavior
- Potential edge cases
- Unknowns

Then start.

---

# 10. Research and Learning

Sometimes implementation reveals that you don't know something.

That's normal.

For example:

> "I need to understand PostgreSQL transactions before implementing this."

Treat this as a **blocker** if you genuinely cannot continue.

```text
Task
 ↓
Blocked
 ↓
Research
 ↓
Understand enough
 ↓
Continue implementation
```

### Important rule

> **Research to unblock implementation, not to avoid implementation.**

Time-box research when possible.

Instead of:

> "I'm going to study PostgreSQL transactions."

Use:

> "I'll spend 45 minutes understanding enough about transactions to implement this feature."

Then return to coding.

---

# 11. Handling Blockers

When you're blocked, identify the reason.

Common blockers:

```text
Unknown technology
Missing information
Bug
External dependency
Client decision
Environment problem
```

Record the blocker on the Trello card.

Example:

```text
BLOCKED

Reason:
Waiting for client to provide the final API credentials.
```

Or:

```text
BLOCKED

Reason:
Need to understand how the payment provider handles webhooks.
```

Don't hide blockers just to keep the board looking clean.

---

# 12. Handling Bugs

When you discover a bug, ask:

> Does this prevent me from completing the current task?

### If no

Create a bug card:

```text
🐛 Fix incorrect date formatting
```

Then continue your current task.

### If yes

Treat it as part of the current work or create a separate blocking task.

```text
Current Task
     ↓
   BLOCKED
     ↓
Fix blocking bug
     ↓
Continue current task
```

Don't send every bug into the backlog automatically.

---

# 13. Keep Work in Progress Small

Try to avoid:

```text
In Progress

🔨 Authentication
🔨 Dashboard
🔨 Database
🔨 API
🔨 UI redesign
```

Instead:

```text
In Progress

🔨 Create authentication callback
```

Finish work before starting more work.

For a solo developer:

> **One major task at a time is a good default.**

---

# 14. Commit Your Work

Make commits around meaningful changes.

Example:

```text
feat: add log submission endpoint
fix: prevent duplicate log submissions
refactor: extract log validation
test: add log endpoint tests
```

Avoid commits like:

```text
stuff
changes
update
final
final2
please work
```

The goal isn't perfect Git history.

The goal is to make your work understandable.

---

# 15. Code Review

Even when working alone, perform a small self-review.

Before marking a task complete, ask:

### Functionality

- Does it actually work?
- Does the main user flow work?

### Edge Cases

- What happens with invalid input?
- What happens when data is missing?
- What happens when the request fails?

### Code Quality

- Is the code understandable?
- Did I duplicate something unnecessarily?
- Did I introduce unnecessary complexity?

### Scope

- Did I build what was requested?
- Did I accidentally add unnecessary features?

---

# 16. Testing

Testing should happen throughout development, not only at the end.

Use the appropriate level of testing.

```text
Manual Test
     ↓
Automated Test
     ↓
Integration Test
     ↓
End-to-End Test
```

You don't need every type of test for every project.

For a small feature, you might simply:

```text
Implement
   ↓
Run locally
   ↓
Test happy path
   ↓
Test obvious failure cases
   ↓
Done
```

For important functionality, add automated tests.

---

# 17. Move to Review / Testing

When implementation is complete:

```text
In Progress
      ↓
Review / Testing
```

Use a checklist.

```markdown
## Verification

- [ ] Main flow works
- [ ] Error case tested
- [ ] No obvious regression
- [ ] Code reviewed
- [ ] Changes committed
```

For UI work:

```markdown
- [ ] Desktop checked
- [ ] Mobile checked
- [ ] Loading state checked
- [ ] Error state checked
- [ ] Empty state checked
```

---

# 18. Definition of Done

A task is Done when:

```text
Implementation complete
        +
Expected behavior works
        +
Relevant testing completed
        +
Code committed
```

Then:

```text
Review / Testing
       ↓
Done
```

"Done" should mean **usable and verified**, not merely "I wrote the code."

---

# 19. Release Planning

When enough work has accumulated to create a meaningful release:

```text
Completed Features
       ↓
Release Candidate
       ↓
Final Testing
       ↓
Deployment
       ↓
Release
```

For a new release, create a release scope.

Example:

```text
v1.1 — Online Payments

Goal:
Allow customers to pay for bookings online.

Features:
- Payment checkout
- GCash
- Payment status
- Payment confirmation
```

Then create the release plan and corresponding Trello tasks.

---

# 20. Client Projects

For freelance projects, add a client communication layer.

The workflow becomes:

```text
Client Requirement
       ↓
Project Brief
       ↓
Requirements / Scope
       ↓
Estimate / Agreement
       ↓
Project Plan
       ↓
Trello
       ↓
Development
       ↓
Testing
       ↓
Client Review
       ↓
Changes
       ↓
Final Approval
       ↓
Release
```

---

# 21. Handling Client Change Requests

Never automatically start a new feature just because the client asks for it.

First determine:

> Is this already included in the agreed scope?

### In scope

```text
Client Request
      ↓
Requirements
      ↓
Trello
      ↓
Development
```

### Out of scope

```text
Client Request
      ↓
Evaluate impact
      ↓
Estimate additional work
      ↓
Client approval
      ↓
Update scope
      ↓
Trello
      ↓
Development
```

This protects you from uncontrolled scope creep.

---

# 22. Client Progress Updates

Give the client a short update periodically.

Use:

```text
# Project Update

## Completed

-
-

## Currently Working On

-

## Next

-

## Blockers

None.

## Client Action Required

-

## Timeline

On track / Delayed / Ahead

Expected completion:
```

Keep it focused on what the client needs to know.

Don't send them your entire engineering task list unless they need it.

---

# 23. Release Workflow for Freelance Projects

For a significant new feature or version:

```text
Client Request
      ↓
Define Release
      ↓
Scope
      ↓
Estimate
      ↓
Client Approval
      ↓
Release Plan
      ↓
Trello Tasks
      ↓
Development
      ↓
Testing
      ↓
Client Review
      ↓
Changes
      ↓
Final Approval
      ↓
Production Release
      ↓
Client Update
```

Example:

```text
Existing Product
      │
      ├── v1.0 — Booking
      │
      ├── v1.1 — Email Notifications
      │
      └── v1.2 — Online Payments
```

Keep the overall project documentation stable while each release gets its own scope and plan.

---

# 24. Deployment

Before deploying:

```markdown
## Deployment Checklist

- [ ] Production environment configured
- [ ] Environment variables configured
- [ ] Database migrations applied
- [ ] Build succeeds
- [ ] Tests pass
- [ ] Production smoke test completed
- [ ] Client-facing functionality verified
```

Then:

```text
Testing
   ↓
Deploy
   ↓
Smoke Test
   ↓
Release
```

---

# 25. Post-Release

After releasing, don't immediately start adding features.

Do a short review.

Ask:

```text
What worked?
What broke?
What did we learn?
What should change?
What should be built next?
```

For a solo project, this can be a few notes in your Decision Log or README.

For a client project, communicate relevant issues and next steps.

---

# 26. Project Maintenance

After release:

```text
Production
    ↓
Bug discovered
    ↓
Assess severity
    ↓
Fix immediately OR
Add to backlog
    ↓
Test
    ↓
Deploy patch
```

Not every bug requires an immediate interruption.

Prioritize based on impact.

---

# 27. When the Project Grows

Don't create a completely new project every time a feature is added.

Use releases:

```text
Project
│
├── v1.0
├── v1.1
├── v1.2
└── v2.0
```

Your documentation can evolve into:

```text
docs/
├── project/
│   ├── brief.md
│   └── decisions.md
│
├── requirements/
│   └── current.md
│
└── releases/
    ├── v1.0/
    │   ├── scope.md
    │   └── plan.md
    │
    └── v1.1/
        ├── scope.md
        └── plan.md
```

Don't create this structure until the project actually needs it.

---

# 28. Recommended Tools

Keep the toolset small.

| Tool              | Purpose                      |
| ----------------- | ---------------------------- |
| **Git**           | Version control              |
| **GitHub/GitLab** | Repository and collaboration |
| **Trello**        | Task management              |
| **Markdown**      | Engineering documentation    |
| **Google Docs**   | Client-facing documents      |
| **CI/CD**         | Automated testing/deployment |
| **Issue tracker** | Optional if project grows    |

You don't need five project-management applications.

---

# 29. The Relationship Between Your Tools

Think of each tool as having one primary responsibility.

```text
                  PROJECT
                     │
        ┌────────────┼────────────┐
        │            │            │
        ▼            ▼            ▼
   Documentation   Trello       Git
        │            │            │
      WHY/WHAT      WORK         CODE
        │            │            │
        │            │            │
        └────────────┼────────────┘
                     │
                     ▼
                  RELEASE
                     │
                     ▼
                   USER
```

### Documentation

Answers:

> Why are we building this?

> What are the requirements?

> What decisions have we made?

### Trello

Answers:

> What should I work on next?

> What's currently in progress?

> What's finished?

### Git

Answers:

> What changed in the code?

> Who changed it?

> When did it change?

---

# 30. The Complete Daily Workflow

When sitting down to work:

```text
1. Check project goal
        ↓
2. Check Trello
        ↓
3. Pick next Ready task
        ↓
4. Understand the task
        ↓
5. Research if necessary
        ↓
6. Create / switch Git branch
        ↓
7. Implement
        ↓
8. Test locally
        ↓
9. Fix problems
        ↓
10. Commit
        ↓
11. Review
        ↓
12. Move Trello card to Done
        ↓
13. Pick next task
```

---

# 31. The Complete Project Workflow

The entire process can be reduced to:

```text
                    DEFINE
                      │
                      ▼
                  PROJECT BRIEF
                      │
                      ▼
                 REQUIREMENTS
                      │
                      ▼
                   PLAN
                      │
                      ▼
                  BACKLOG
                      │
                      ▼
                    READY
                      │
                      ▼
                 DEVELOPMENT
                      │
              ┌───────┴───────┐
              │               │
            Blocked         Working
              │               │
              ▼               ▼
          Research /       Implement
          Resolve          & Test
              │               │
              └───────┬───────┘
                      ▼
                   REVIEW
                      │
                      ▼
                    DONE
                      │
                      ▼
                  RELEASE
                      │
                      ▼
                 PRODUCTION
                      │
                      ▼
                  MAINTAIN
                      │
                      └──────► BACKLOG
```

---

# 32. The Rules

If you want to keep the entire workflow simple, remember these rules.

### Rule 1 — Define before building

Know what problem you're solving.

### Rule 2 — Keep the MVP small

Don't build everything you can imagine.

### Rule 3 — Break work into meaningful tasks

One task should have a clear outcome.

### Rule 4 — Work on a small number of things

Prefer finishing over starting.

### Rule 5 — Research when blocked

But research only enough to continue.

### Rule 6 — Test while developing

Don't leave all testing until the end.

### Rule 7 — Define Done

Know what completion means.

### Rule 8 — Record important decisions

Don't document every thought.

### Rule 9 — Treat scope as a boundary

Especially when working with clients.

### Rule 10 — Release working software

The goal isn't a perfect Trello board.

The goal isn't perfect documentation.

The goal isn't perfect architecture.

> **The goal is to build, ship, learn, and improve.**

---

# 33. Minimal Workflow

If the full workflow feels like too much, reduce it to this:

```text
PLAN
  ↓
CREATE TASK
  ↓
BUILD
  ↓
TEST
  ↓
DONE
  ↓
SHIP
```

Use the more detailed workflow only when the project actually requires it.

For a solo developer, **simple and consistently followed beats sophisticated and abandoned.**
