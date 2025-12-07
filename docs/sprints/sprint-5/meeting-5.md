---
title: Meeting with customer #6
parent: ITPD Assignment 6
nav_order: 2
layout: default
---

# Meeting with customer #5

> Date: 05.12.2025
> Participants: @markovav-official @fil-126 Customer

### Action Points

1.  **Team:** Finalize and deploy the "Assignment Task Files" and "Student Submission" features to the Production environment by **Monday, 08.12.2025**.
2.  **Team:** Grant the Customer (Instructor) the "Student" role within any group so they can verify the user experience.
3.  **Customer:** Adopt the application as the primary grading tool for the course, replacing the Google Sheet.
4.  **Team:** Actively monitor production logs and metrics via Grafana to ensure stability during the transition.

---

### Meeting Summary

The team met with the customer to demonstrate the live Production environment and coordinate the official launch of the grading tool.

**1. Production Grading Demo**

The team demonstrated the fully functional grading workflow on the live production server. The customer verified that they could grade students and that the privacy controls (students seeing only their own and their group grades) were functioning correctly.

**2. Transition from Google Sheets**

The customer confirmed their decision to immediately stop using Google Sheets and switch to this application as the sole grading tool for the course.
* **Requirement:** To support this transition, the customer requires the ability to upload assignment instructions and for students to upload submissions directly.
* **Deadline:** The team committed to deploying these specific features by **Monday, December 8th, 2025**.

**3. Student View Access**

The customer requested the ability to view the system as a student to ensure the grades look correct from that perspective.
* **Decision:** The team will add the Instructor's account to the system with a secondary "Student" role for testing purposes.

**4. Production Monitoring (Grafana)**

The team demonstrated their readiness for live traffic by showing their Grafana dashboard. They explained how they collect logs and metrics to analyze the current state of the application. This ensures the team can proactively detect and resolve any issues users might face during the rollout without waiting for support tickets.
