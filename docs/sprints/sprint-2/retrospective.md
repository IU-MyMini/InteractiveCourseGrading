---
title: ITPD Assignment 3
permalink: /sprints/sprint-2/
has_children: true
nav_order: 3
layout: default
---

# Sprint 2 Retrospective

**Date:** November 15, 2025

This document outlines the team's reflection on Sprint 2, including our successes, challenges, and actionable plans for improvement in Sprint 3.

---

### What went well?

1.  **Prototype Feedback Loop:** We successfully iterated on our Figma prototype based on the customer's feedback from Sprint 1. We changed the professor's view to be "group-first," which the customer confirmed was the correct workflow.
2.  **Initial Deployment Milestone:** We achieved a major technical goal by successfully deploying the initial "shell" of our module to the university's staging server. This unblocks future work on providing real-time access to the customer.
3.  **Clear Communication with Customer:** Our sprint review meeting was productive. We clearly communicated a major blocker (Moodle API) and, in response, received a clear, high-priority request from the customer (get a "clickable" version live).

---

### What problems did you encounter?

1.  **[Problem] Moodle API Access Denied**
    * Our request for Moodle API access was formally denied by the university administration (Alexey Potemkin).
    * **Root Cause:** This is a political and policy-based problem, not a technical one. The administration is concerned that providing API access will encourage professors to abandon Moodle for other platforms.
    * **Solution:** This is only partially resolved. Our customer has offered to personally escalate the issue and advocate for our project. In parallel, our technical backup plan is to build a manual import/export feature, but this is a suboptimal solution.

2.  **[Problem] Deployed Version is Not Yet Usable for Feedback**
    * While we successfully deployed the module "shell," it is not yet functional. The customer's primary request was to "click around" and provide feedback on the real application, which he cannot do.
    * **Root Cause:** This is a natural part of the development process. We have deployed the container, but we have not yet connected the backend APIs to the frontend or populated a staging database.
    * **Solution:** This becomes the top priority for Sprint 3.

---

### What will you change in the next Sprint?

| Priority | Actionable Change | Rationale |
| :--- | :--- | :--- |
| **High** | **Get a "clickable" MVP to staging.** We will connect the backend APIs (e.g., login, create/view assignments) to the deployed frontend. | The customer explicitly stated this is his #1 priority. He needs a functional, even if "crooked," version to provide the next level of feedback. |
| **High** | **Actively follow up on the Moodle API blocker.** We will provide our customer with any information he needs to support his discussion with the administration. | This is our biggest external dependency. If it's not solved, it will force us to change our architecture to support a manual import/export workflow. |
| **Medium** | **Begin development on next-priority features.** Based on the approved prototype, we will start building the logic for viewing/editing individual grades within the group view. | This is the next logical feature in our roadmap, and the design is now confirmed. |
| **Medium** | **Draft our formal Test Plan.** | The customer mentioned that the next course assignment is on testing, so we must formally document our testing strategy (unit, integration, and E2E). |

---

**For Sprint 3, we will apply the following 2 actions:**

1.  **(High) Get a "clickable" MVP to staging.**
2.  **(High) Actively follow up on the Moodle API blocker.**
