---
title: ITPD Assignment 7
permalink: /sprints/sprint-6/
has_children: true
nav_order: 7
layout: default
---

# Sprint 6 Retrospective

**Date:** 13 December 2025

This document outlines the team's reflection on Sprint 6, including our successes, challenges, and actionable plans for the final push in the next sprint.

---

### What went well?

1.  **Seamless File Management Deployment:** We successfully delivered the "Assignment Task Files" and "Student Submission" features on time. The customer was able to verify the flow of uploading task descriptions and seeing them as a student.
2.  **Optimized Grading Workflow:** The implementation of the "download submission" button directly within the grading table was a success. It allows the instructor to download files and input grades in a single view, streamlining their work.
3.  **Adherence to Strict Deadlines:** We met the aggressive deadline set in the previous meeting (Monday, 08.12) for the submission features, which maintained the customer's trust and allowed them to continue using the tool for the course.

---

### What problems did you encounter?

1.  **[Problem] Compression of the Peer Review Timeline**
    * **Context:** The customer explicitly asked to "fastly finish" the peer-review part to finalize the project within the next week.
    * **Root Cause:** Peer Review is the most complex logic in the system, and it was scheduled for the very end of the roadmap, leaving little buffer for error before the course concludes.
    * **Solution:** We have decided to halt all other non-essential development and refactoring to dedicate 100% of our velocity to Peer Review in the next sprint.

2.  **[Problem] Managing Scope Creep vs. Finalization**
    * **Context:** As the customer uses the tool, new minor UX requests appear, but we are entering the finalization phase.
    * **Root Cause:** The system is now live, so user feedback is immediate, distracting from the remaining core feature (Peer Review).
    * **Solution:** We are enforcing a "Feature Freeze" on everything except Peer Review and critical bug fixes.

---

### What will you change in the next Sprint?

| Priority | Actionable Change | Rationale |
| :--- | :--- | :--- |
| **High** | **Exclusive Focus on Peer Review:** The entire team will work on this single feature. | The customer requires the project to be finalized next week, and this is the last missing piece. |
| **High** | **Daily Integration Checks:** We will merge frontend and backend logic for Peer Review daily rather than at the end of the sprint. | With only one week left to finalize the project, we cannot afford a "merge hell" or integration issues on the final day. |
| **Medium** | **Scope Freeze:** Reject any new feature requests regarding the Gradebook or Submissions until Peer Review is done. | We must ensure the "Project Finalization" goal is met without distraction. |
| **Low** | **Documentation Prep:** Begin compiling the final handover documentation. | Required for the project closeout next week. |

---

**For the next Sprint, we will apply the following 2 actions:**

1.  **(High) Exclusive Focus on Peer Review:** We will implement the assigning and reviewing logic immediately.
2.  **(High) Daily Integration Checks:** We will ensure the complex peer-matching logic works on Production day-by-day.
