---
title: ITPD Assignment 4
permalink: /sprints/sprint-3/
has_children: true
nav_order: 4
layout: default
---

# Sprint 3 Retrospective

**Date:** November 22, 2025

This document outlines the team's reflection on Sprint 3, including our successes, challenges, and actionable plans for improvement in Sprint 4.

---

## What went well?

- **Successful Deployment of the Grading Table:** We successfully transitioned from Figma prototypes to a live, functional deployed application. The core logic for the "Group-first" view and the "Group vs. Individual" grade columns is working correctly on the staging server.
- **Stakeholder Validation:** The customer explicitly validated our design choices during the demo. The specific layout adjustments we made in Sprint 2 (group-centric view) were approved without major changes, saving us from potential rework.
- **Access & Engagement:** We resolved the previous bottleneck regarding customer access. The stakeholder is now successfully logged into the staging environment and can provide direct feedback by "clicking around," which has tightened our feedback loop.

## What problems did you encounter?

- **Blocker: Moodle API Access Denial**
  - **Root Cause:** University administrative policies are resistant to allowing external API access due to fears of professors abandoning the official Moodle platform.
  - **How we handled it:** We shifted our strategy from "Integration First" to "Standalone Excellence." Instead of fighting for access now, we decided to build a fully functional standalone MVP to demonstrate superior usability first, as advised by the customer.

- **Ambiguity in MVP Scope vs. Deadlines**
  - **Root Cause:** We had multiple competing features (Peer Review, Group Selection, Student View) in the backlog without a clear prioritization for the upcoming course deadline.
  - **How we handled it:** During Meeting #4, we forced a decision on the next milestone. We established a hard deadline (December 1st) and explicitly deprioritized other features to focus solely on the "Student View" to ensure a shippable product.
  
## Actionable Changes for Sprint 4

| Priority | Change | Action Plan |
|----------|----------|-------------|
| High     | Narrow Focus to "Student View" | Stop all work on "Peer Review" and "Group Self-Selection." Dedicate all engineering resources to implementing Student Login and Grade View to meet the Dec 1st deadline. |
| High     | Production-First Deployment | Move from "deploy to staging when ready" to "deploy to production ASAP." We will set up the production environment immediately to identify infrastructure issues before the hard deadline. |
| Medium   | Manual Data Strategy | Since the API is blocked, we will implement a robust CSV import or manual data entry method for the TAs so the system is usable on Day 1 without Moodle integration. |
