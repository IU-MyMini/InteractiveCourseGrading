---
title: Meeting with customer #2
parent: ITPD Assignment 2
nav_order: 2
layout: default
---

# Meeting with customer #2

> Date: 07.11.2025
>
> Participants: @markovav-official @fil-126 Customer

## Meeting summary

The development team met with a stakeholder to demonstrate the initial prototypes for the new ITPD Learning Management
System (LMS) and gather feedback. The team presented mockups for both the student and professor/TA views, leading to
several key decisions on layout and functionality.

### 1. Student View Feedback

* **Assignment Order:** The stakeholder strongly recommended that the assignment list be shown in **reverse
  chronological order** (newest assignment on top). This solves a major usability issue from Moodle, where students must
  always scroll to the bottom to find the current week's tasks.
* **Grade Display:** The student dashboard should display **two separate columns** for grades: one for the **"Group
  Grade"** and one for the **"Individual Grade."** This clarifies how a student's personal contribution (or lack
  thereof) affects their final score relative to the team's overall performance.

### 2. Professor/TA View Feedback

* **Default Gradebook View:** The primary gradebook view for TAs and professors should be organized **by group**, not by
  individual students. The preferred workflow is to see a list of all groups, click on a specific group, and *then* see
  the list of students and grades within that group.
* **Assignment Document Upload:** The stakeholder praised the plan to have a single upload location for an assignment's
  description (e.g., the PDF). This is a significant improvement over the current Google Sheet, which requires TAs to
  copy-paste the same link for every single group.

### 3. Core Functionality Decisions

* **Group Management:**
    * **TAs/Admins** will be responsible for **creating the group "shells"** (e.g., creating "Project A - Group 1," "
      Project A - Group 2").
    * **Students** will then **self-join** the groups they belong to.
    * TAs/Admins must have an **override function** to manually move students between groups (e.g., for late joiners or
      to correct mistakes).
* **Peer Review Workflow:**
    * **MVP Plan:** For the initial version, TAs will **manually assign** which group reviews which other group.
    * **Future Goal:** This should be an automated, "rolling" (round-robin) assignment to prevent collusion and ensure
      groups don't review the same team repeatedly.
    * **Grading:** When submitting a peer review, students will be required to **enter a numerical grade directly into
      the system** (in addition to any review document). This grade will become the "Group Grade" for the team being
      reviewed. The TA will then grade the *quality* of the review itself, which will become the "review" grade for the
      student who submitted it.
* **Individual Grade Logic:** The team and stakeholder agreed to **postpone the complex logic** for calculating
  individual grades. The initial priority is to get the group grading, submission, and peer-review workflows
  functioning. For the MVP, the "Individual Grade" column can simply mirror the "Group Grade."

### 4. Technical & Admin

* **Repository Strategy:** The stakeholder clarified that his previous "monorepo" comment was simply to ensure the
  *entire team* works from **one shared repository**, not (as some past teams had done) creating separate repositories
  for each team member.
* **Frontend/Backend:** The team's plan to work on their backend (C#) and specific frontend modules that plug into the
  main university portal is acceptable, as long as the backend API is well-documented (e.g., with Swagger).

### 5. Next Steps

The stakeholder's primary request was to get hands-on access. The team agreed to provide login credentials to the **test
environment** as soon as possible so the stakeholder can "click around" and provide more tangible feedback.
