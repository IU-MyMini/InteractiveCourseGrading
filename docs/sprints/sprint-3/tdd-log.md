---
title: TDD log
parent: ITPD Assignment 4
nav_order: 3
layout: default
---

# TDD Log - Sprint 3

- Task: Implementation of Grading Table Logic (Group vs. Individual Grades)
- Issue: [#34](https://github.com/IU-MyMini/InteractiveCourseGrading/issues/34)
- TDD Cycles: 1

## Key commits

### Init test
[Commit](https://github.com/IU-MyMini/Backend/pull/4/commits/cf898740b51324c0df06b16fa11a52523b1ff420) | [Workflow Run](https://github.com/IU-MyMini/Backend/actions/runs/19598326554/job/56126125135)

### Pass the test
[Commit](https://github.com/IU-MyMini/Backend/pull/4/commits/d386ecc30032eefd41d0dff895f8ee335bbf1b49) | [Workflow Run](https://github.com/IU-MyMini/Backend/actions/runs/19598363471/job/56126207240)

### Refactor
[Commit](https://github.com/IU-MyMini/Backend/pull/4/commits/7b4b9f4063389575ce8b8fe9f4a8a02c715dbb4b) | [Workflow Run](https://github.com/IU-MyMini/Backend/actions/runs/19598410134/job/56126318635)

## Reflection: TDD vs. Previous Approach

Adopting TDD for the grading table implementation significantly shifted our workflow from reactive debugging to proactive design. In our previous approach, we would often build the full UI and then repeatedly patch the backend when data didn't display correctly, leading to regression cycles. With TDD, specifically when implementing the "Group vs. Individual" grade logic, we were forced to define the exact data structure for the API response before writing a single line of controller code. This meant that when we finally connected the frontend, the data contract was already verified, resulting in a much smoother integration and zero logic bugs during the deployment to staging. However, it is important to note that this process was much more time consuming than our previous development approach.
