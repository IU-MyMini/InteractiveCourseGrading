---
title: Meeting with customer #3
parent: ITPD Assignment 3
nav_order: 2
layout: default
---

# Meeting with customer #3

> Date: 14.11.2025
> Participants: @markovav-official @fil-126 Customer

### Action Points

1.  **Team:** Provide the customer with login credentials to the deployed staging (test) environment as the top priority. The goal is to allow the customer to "click around" and create test assignments.
2.  **Team:** Continue investigating the Moodle API access issue.
3.  **Customer:** Offered to personally contact Alexey Potemkin to discuss the Moodle API access request and advocate for the project.
4.  **Team:** Prepare for the upcoming "Testing" assignment and work on making the deployed system stable enough for initial user feedback.

---

### Meeting Summary

The team met with the customer to review progress from Sprint 2.

**1. Prototype and Feedback:**
The team presented an updated Figma prototype that directly addressed the customer's previous feedback. The TA/Professor view now defaults to a "group-first" layout, which the customer approved. The new design allows the professor to expand a group to see individual student grades for different assignment components.

**2. Deployment Status:**
The team confirmed that the application module has been successfully deployed to the university's staging server. While the API endpoints are not yet functional, the service is running.

**3. Blocker: Moodle API Access**
The main discussion point was a significant blocker. The team's request for Moodle API access was denied by Alexey Potemkin.
* **Reason for Denial:** The university is concerned that providing API access will encourage professors to "leave" Moodle and use external platforms.
* **Team's Counter-Argument:** The team explained that their tool is just a different interface, and all data would sync *back* to Moodle, improving data integrity. They argued that *not* providing access simply encourages professors to continue using Google Sheets, which is a worse outcome for the university.
* **Customer's Response:** The customer strongly agreed, stating, "The professor has *already left* Moodle for Google Sheets." He offered to speak with Potemkin directly to support the request.

**4. Strategic Plan & Next Steps:**
The customer advised the team on how to handle organizational resistance. He suggested that the best strategy is to deliver a fully working product (even without integration) and then demonstrate its clear superiority. Once the value is proven, it's much easier to make the case for the "small missing piece" of API access.

The meeting concluded with the customer's primary request: to get access to the staging environment as soon as possible, even in a "crooked" or incomplete state, so he can begin testing it and providing feedback.
