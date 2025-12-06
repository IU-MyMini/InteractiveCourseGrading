---
title: ITPD Assignment 6
permalink: /sprints/sprint-5/
has_children: true
nav_order: 6
layout: default
---

# Sprint 5 Retrospective

**Date:** December 06, 2025

This document outlines the team's reflection on Sprint 5, including our successes, challenges, and actionable plans for
improvement in Sprint 6.

---

## What went well?

1. **Production Readiness:** We successfully deployed a stable, fully functional grading workflow to the Production
   environment. We moved beyond "staging" and now have a live system ready for the customer to use as their primary
   tool.
2. **Customer Adoption:** We achieved a major product milestone: the customer explicitly confirmed they will stop using
   Google Sheets and switch to our application immediately. This validates our value proposition.
3. **Observability Setup:** The implementation of Grafana for logs and metrics was a success. It allowed us to
   demonstrate system health to the customer during the meeting, building trust in our ability to support live users.

## What problems did you encounter?

### What problems did you encounter?

1. **[Problem] Instructor lacked ability to verify "Student View"**

* **Context:** The customer wanted to verify exactly what students see (privacy of grades) before releasing real grades,
  but their "Instructor" account didn't allow this view.
* **Root Cause:** Our Role-Based Access Control (RBAC) was designed too rigidly. We didn't anticipate the need for an
  Instructor to "impersonate" or act as a Student for testing purposes.
* **Resolution:** We agreed on a workaround: we will manually add the Instructor's account to a specific testing group
  with the "Student" role.

2. **[Problem] Urgent feature gap for full adoption (File Submissions)**

* **Context:** While grading works, the customer cannot fully switch from Google Sheets without the ability to upload
  assignment instructions and receive student files.
* **Root Cause:** The adoption timeline accelerated. The customer decided to switch *now*, whereas we had planned the
  submission features for later in the roadmap.
* **Resolution:** We re-prioritized the backlog and committed to an aggressive deadline (Monday, Dec 8th) to deliver
  these specific features.

## Actionable Changes for Sprint 4

| Priority   | Actionable Change                                                                                                                               | Rationale                                                                                                                                 |
|:-----------|:------------------------------------------------------------------------------------------------------------------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------|
| **High**   | **Immediate Focus on Submission & Task Files:** Dedicate all development resources to finishing file upload logic by Monday.                    | This is the blocking requirement for the customer to officially adopt the tool next week.                                                 |
| **High**   | **Proactive Log Monitoring:** Assign a team member to check Grafana logs daily during the first week of live usage.                             | As real students start using the system, we need to catch 500 errors or logic bugs immediately, rather than waiting for email complaints. |
| **Medium** | **Implement "Test Student" Role Standard:** Create a standard process (or script) to easily grant "Student" roles to Admin/Instructor accounts. | This will recur as a need; Instructors will always want to verify how a new assignment looks to students.                                 |
| **Low**    | **UI Polish for Gradebook:** Improve the spacing and mobile responsiveness of the grade input table.                                            | While functional, the layout is a bit dense on smaller screens.                                                                           |