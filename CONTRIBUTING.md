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

# Our Sprint Cycle

We operate in **one-week sprint cycles** to maintain a fast and consistent feedback loop with our stakeholders.

1.  **Sprint Planning (Monday):** The team meets to review the `Backlog` on our GitHub Project board. We select high-priority tasks that align with our roadmap, break them into concrete GitHub Issues, and assign them. These tasks form our **Sprint Goal**.
2.  **Development (Tuesday-Friday):** Team members work on their assigned issues, following the Git Workflow detailed below.
3.  **Sprint Review (Saturday):** We hold a recorded meeting with our customer (stakeholder). We demo the new, functional features (our "Done" work), gather live feedback, and reprioritize the `Backlog` if needed.
4.  **Retrospective (Saturday):** Immediately after the customer meeting, the development team meets internally to discuss what went well, what went wrong, and what we will change to improve our process for the *next* sprint.

# Git Workflow

Our workflow is a simplified version of **GitHub Flow** (inspired by [guides.github.com/introduction/flow](https://guides.github.com/introduction/flow/)). Its purpose is to ensure the `main` branch is **always stable and deployable**, and that no code is integrated without a proper peer review.

### Branching Rules

* **`main`:** This is our single, protected, and stable branch. It represents the official, "live" state of our project.
* **Feature Branches:** All new work (features, fixes, docs) **must** be done on a separate branch.
    * **Naming Convention:** We use the `type/description` format. This helps us instantly understand the purpose of a branch.
        * `feature/add-group-grading`
        * `fix/student-login-crash`
        * `docs/update-contributing-md`

This branching model is simple and effective. It isolates all in-progress work from the stable `main` branch, preventing "work-in-progress" code from breaking our app.

### Secrets management

- For local environment, we use secrets.json file. This file is located in API project directory, and it is ignored during commits (see [.gitignore](https://github.com/IU-MyMini/Backend/blob/master/.gitignore)). There is example.secrets.json file with dummy values that provides the structure and needed secrets for the module.
- For staging environment, we use environment files with structure similar to secrets.json. 
- For production environment, we use kubernetes environment config.

# Branch Protection Rules

The main branch is protected by the following rules.

## **Rule 1**: Require a Pull Request before merging.

**Justification**: This is our primary quality gate. It prevents all direct pushes to main and forces every change to be documented in a Pull Request.

## **Rule 2**: Require at least one approval from a team member.

**Justification**: This enforces our peer-review process. It ensures a second pair of eyes has reviewed the code for bugs, style, and adherence to the requirements before it's merged.

# Commit Message Format

We use Conventional Commits (inspired by www.conventionalcommits.org).

Format: <type>: <short description>

Common Types:
- feat: (A new feature)
- fix: (A bug fix)
- docs: (Documentation changes)
- style: (Code formatting, missing semicolons, etc.)
- refactor: (Code changes that neither fix a bug nor add a feature)
- test: (Adding or fixing tests)
- chore: (Build process, package manager updates)

**Justification**: This format creates a clean, readable, and structured Git history. It makes it easy to understand what changed and why just by looking at the commit logs.

# Issue and Pull Request (PR) Templates

- Issue Template: Our issue template requires:
  - User Story: (As a [role], I want [feature] so that [benefit])
  - Acceptance Criteria: (A checklist of what "Done" means)
  - **Justification**: This forces us to clearly define a task before starting it, preventing ambiguity and ensuring the developer knows exactly what to build.
- Pull Request Template: Our PR template requires:
  - Link to Issue: (e.g., Closes #12)
  - Description of Changes: (What was done?)
  - How to Test: (Steps for the reviewer to verify the changes)
  - **Justification**: This gives the reviewer all the context they need to approve the PR efficiently, saving time and improving the quality of the review.
 
# Pull Request Review Process

- When a developer finishes their task, they push their feature branch and open a Pull Request (PR) to merge into main.
- The PR must link to the GitHub Issue it resolves.
- The developer assigns at least one other team member as a reviewer.
- The reviewer checks the code against the Issue's Acceptance Criteria, looks for bugs, and ensures code quality.
- The reviewer either approves the PR or requests changes.
- Once approved, the original author of the PR is responsible for merging it into main and deleting the feature branch.

**Justification**: This process distributes knowledge across the team (preventing knowledge silos), catches bugs early, and enforces a consistent quality standard.

# Deployment Strategy

### Environments

* **Staging Environment:** This is our primary test environment, deployed within the `my.innopolis.university` infrastructure.
* **Production Environment:** This will be the final, live application used by ITPD students.

### Deployment Process

1.  All code merged into the `main` branch is considered "ready for staging."
2.  We will perform a **manual deployment** from the `main` branch to the **staging environment** at the end of each sprint.
3.  **Stakeholder Access:** Our customer and TAs are given the URL to this staging environment. This allows them to "click around" and test our latest stable features at any time.
4.  Once we have a feature-complete MVP that is approved by the stakeholder on staging, we will perform a manual deployment to the **production environment** for live use.

**Justification:** This process ensures that stakeholders are always testing a stable version (not a broken `feat` branch) and gives us a final quality check before releasing to real users.

# License

We have chosen the **GNU General Public License v3.0 (GPL-3.0)** for this project.

**Justification:** The GPL-3.0 is a strong "copyleft" license. It guarantees that this project, and any modifications or derivative works built upon it, must also be released under the same open-source license.

Given this is a project for the university, this license is ideal for two reasons:
1.  It protects the "open" nature of the work.
2.  It ensures that future students and the university can continue to use, modify, and build upon this project freely, with the source code always remaining available.

# GitHub Projects

We use **GitHub Projects** to manage our entire development workflow and track all tasks.

* **Views & Order:** Our project board is a **Kanban** board. The columns are ordered to represent the flow of a task from idea to completion.

    1.  **Backlog:** All potential tasks, user stories, and ideas. This is our "icebox" of things we *might* do.
    2.  **To Do (Sprint):** Tasks we have committed to completing in the current one-week sprint. These are pulled from the `Backlog` during Sprint Planning.
    3.  **In Progress:** What team members are actively working on *right now*. A task should only be here if someone is coding it.
    4.  **In Review:** Tasks that are "code complete" and have an open Pull Request waiting for peer review.
    5.  **Done:** Tasks that have been reviewed, approved, and successfully merged into the `main` branch.

**Justification:** This board provides a single source of truth for the status of all work. It allows any team member (or stakeholder) to see our progress at a glance and identifies potential bottlenecks (e.g., if many tasks are stuck "In Review").
