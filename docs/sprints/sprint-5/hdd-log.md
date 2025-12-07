---
title: HDD log
parent: ITPD Assignment 6
nav_order: 3
layout: default
---

# HDD Log - Sprint 5

## Selected Input Metric

**Metric:** `http_requests_received_total{code="200", endpoint="api/Grading/Grade"}` (number of grading submissions).

**Why this metric?**

* It directly influences our North Star Metric: *Assignments Fully Graded*.
* It is easy to measure using default prometheus-net metrics.
* It reflects real instructor activity and engagement with the grading flow.
* It is sensitive to friction in the UI/UX or backend reliability.

## Current Value

(From test environment)

* **6 grading requests per day** on average (team testing only).

## Hypotheses

### Hypothesis 1

**"We believe that adding a clearer 'Grade Submission' button for instructors will result in more completed grading actions when instructors open a submission page because the current button placement is easy to overlook."**

### Hypothesis 2

**"We believe that reducing the number of steps required to grade will result in more grading submissions when instructors grade many assignments at once because reducing friction makes the workflow faster."**

### Hypothesis 3

**"We believe that improving backend response time for grading will result in more successful grading submissions when instructors grade during peak load because long latencies discourage continuing the grading flow."**

## Selected Hypothesis

**Chosen Hypothesis:** Hypothesis 1

**Why?**

* It is the fastest change to implement (pure frontend change).
* It introduces no backend risk.
* It directly impacts the number of grading request events fired.
* Usability issues were already noticed during internal demos.

## Implemented Change

* Updated the UI to make the **"Grade Submission"** button visually prominent.
* Moved its position to the top-right corner of the submission view.
* Added a secondary shortcut button at the bottom of the page.
* Deployed changes to the development environment.


## Test Traffic Generation

The team performed the following flow:

* Each team member graded **3–4 assignments** using the updated UI.
* Total generated test events: **10 grading submission requests**.

## Evidence

* prometheus-net metrics page shows increased counter values for the POST grading endpoint.
* VictoriaMetrics graph (via Grafana) displays a spike in `http_requests_received_total{code="200", endpoint="api/Grading/Grade"}` after deployment.
* Logs in VictoriaLogs confirm grading actions (request + response entries).

## Estimates

### How many real users would be enough?

**Estimate:** ~15 instructors.

**Justification:**

* Typical grading behavior varies a lot per instructor.
* With 15 users, even if each performs only a small number of grading actions, total events should be sufficient to detect a pattern.

### How much data would be enough?

**Estimate:** **200–300 grading events.**

**Justification:**

* This gives enough granularity to compare pre-change and post-change request volume.
* Counter metrics smooth out noise, so a few hundred events allow us to detect a clear uplift.
