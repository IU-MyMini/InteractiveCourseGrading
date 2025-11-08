# Tactical Plan

This document outlines our team's workflow, development process, and quality standards. Following this plan will help us
stay organized, maintain code quality, and meet our project goals.

## 1. How will you track tasks that need to be done for the project?

All project work is tracked using two main tools:

* **GitHub Issues:** Every new feature, bug, or chore is logged as an **Issue**. Issues are the single source of truth
  for *what* needs to be done. They should be descriptive and include acceptance criteria (what it means for the task to
  be "done").
* **GitHub Project Board:** We use a Kanban-style **Project Board** to visualize the status of all current issues. The
  board will have columns like `Backlog`, `To Do (Sprint)`, `In Progress`, and `Done`.

This system provides a clear, real-time overview of our progress, which we will review during our weekly planning
meetings.

## 2. How will you assign tasks to your teammates?

Tasks will be assigned during our **weekly planning meeting**:

1. We will review the `Backlog` and select the highest-priority tasks for the upcoming one-week sprint, moving them to
   the `To Do (Sprint)` column.
2. Team members will then **self-assign** tasks from the `To Do (Sprint)` column based on their skills, interests, and
   current workload. This encourages ownership and balanced effort.
3. The assignment is formally made by adding the team member as the "Assignee" on the GitHub Issue.

## 3. How will you ensure a certain quality of a task completion?

We enforce quality primarily through our development workflow. We use a **GitHub Flow** model:

1. **Branch Protection:** The `main` branch is **protected**. No one can push code directly to `main`.
2. **Feature Branches:** All work must be done on a separate feature branch, usually named `feature/...` or `fix/...`.
3. **Pull Requests (PRs):** When a task is complete, the developer opens a **Pull Request (PR)** to merge their feature
   branch into `main`.
4. **Mandatory Peer Review:** A PR **must be reviewed and approved by at least one other team member** before it can be
   merged.
    * Reviewers are responsible for checking code quality, logic, and ensuring the changes match the requirements of the
      GitHub Issue.
    * This "peer review" step is our primary quality gate.
5. **Automated Checks (Future):** We will aim to integrate automated checks (like linters or tests) that must pass
   before a PR can be merged.

## 4. How will you verify that a task is done?

A task (GitHub Issue) is only considered **"Done"** when it meets our "Definition of Done":

* All code for the feature has been written.
* The code has been pushed to its feature branch.
* A Pull Request has been opened, reviewed, and **approved** by at least one teammate.
* The Pull Request has been successfully **merged** into the `main` branch.
* The feature branch has been deleted.
* The corresponding GitHub Issue is **closed** and moved to the `Done` column on our Project Board.

## 5. What are you planning to do with tasks that are not completed in one iteration?

Our iterations (sprints) are one week long. If a task is not "Done" (see definition above) by the time of our next
weekly planning meeting:

* The task will be **moved back** from `In Progress` to the `To Do (Sprint)` or `Backlog` column.
* The team will briefly discuss *why* it wasn't completed (e.g., it was blocked, it was larger than expected, priorities
  changed).
* The task will then be **re-prioritized** along with all other backlog items for the upcoming sprint.