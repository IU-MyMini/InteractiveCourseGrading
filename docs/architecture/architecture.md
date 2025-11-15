---
title: Architecture
permalink: /architecture/
has_children: true
nav_order: 201
layout: default
---

# Architecture

## Table of contents

* [Interactive prototype](#interactive-prototype)
* [Context diagram](#context-diagram)
* [Use case diagram](#use-case-diagram)
* [Component diagram](#component-diagram)
* [Sequence diagrams](#sequence-diagrams)
    * [QAST002-1](#qast002-1)
    * [QAST005-1](#qast005-1)
* [Design decisions](#design-decisions)

## Interactive prototype

Figma
prototype: [Grading Module Design](https://www.figma.com/design/tQQktvmjVIhOpM61luAvF8/InteractiveCourseGradingDesign?node-id=0-1&t=2s9zfvzOJvSswROL-1)

## Context diagram

```mermaid
graph TD
    subgraph "Interactive Course Grading System"
        System[Interactive Course Grading System]
    end

    subgraph "External Actors"
        Student[Student]
        Instructor[Course Instructor]
        TA[Teacher Assistant]
        Admin[System Admin]

        SSO[IU Single Sign-On]
        Moodle[IU Moodle]
    end

    Student <-->|View grades| System
    Student <-->|View assignments| System
    Student <-->|Submit assignment| System
    Student <-->|Submit peer-review| System
    
    TA <-->|View all grades| System
    TA <-->|Create assignment| System
    TA <-->|Grade assignment| System
    TA <-->|Manage groups| System
    TA <-->|Assign peer-reviewer for assignment| System

    Instructor <-->|View all grades| System
    Instructor <-->|Create assignment| System
    Instructor <-->|Grade assignment| System
    Instructor <-->|Manage groups| System
    Instructor <-->|Assign peer-reviewer for assignment| System
    Instructor <-->|Manage TAs| System

    Admin <-->|Manage courses| System
    Admin <-->|Assign instructors| System

    System <-->|Authorize user|SSO
    System <-->|Synchonize grades| Moodle
    System <-->|Synchonize submissions| Moodle
```

## Use case diagram

![Use case diagram](assets/use-case-diagram.png)

### Component diagram

![Component diagram](assets/component-diagram.png)

### Sequence diagrams

#### QAST002-1

![QAST002-1](assets/sequence-diagram-qast002-1.png)

#### QAST005-1

![QAST005-1](assets/sequence-diagram-qast005-1.png)

#### User Story: Grading

![User Story: Grading](assets/sequence-diagram-user-story-grading.png)

#### User Story: Grades View

![User Story: Grades View](assets/sequence-diagram-user-story-grades-view.png)

## Design decisions

| Driver | Decision | Rationale | Discarded Alternatives |
|--------|----------|-----------|------------------------|
| **SEC-1:** Secure & Seamless User Authentication | Integrate with the existing **Innopolis University Single Sign-On (SSO)** | - Leverages existing, secure university infrastructure<br>- Provides a seamless UX for students and staff (no new account needed)<br>- Avoids the high risk and maintenance burden of managing credentials | - **Custom email/password system:** High security risk, poor UX, and difficult to maintain user lists<br>- **Third-party OAuth (e.g., Google):** Doesn't confirm user's role within the university |
| **SEC-2:** Role-Based Data Privacy | Implement a strict **Role-Based Access Control (RBAC)** system | - Critical requirement: Students *must* only see their own grades<br>- Provides distinct, tailored functionality for Students, TAs, Instructors, and Admins<br>- Simplifies permission management | - **No RBAC:** Insecure and leaks private student data<br>- **Manual permissioning:** Does not scale and is error-prone |
| **CON-1:** Integration with `my.innopolis.university` | Build the application as an **independent service/module** to be plugged into the existing portal | - Allows for independent development, deployment, and scaling<br>- Focuses effort on the core business problem (grading)<br>- Provides a unified entry point for users via the main portal | - **Monolithic architecture:** Impossible, as we don't own the main university portal<br>- **Full microservices:** Over-engineering for a single, well-defined problem domain |
| **QA-1:** Universal Accessibility | Develop a **responsive web application** as the primary user interface | - Accessible from any device (laptop, tablet, phone) via a web browser<br>- No installation required for users<br>- Single codebase is easier to maintain and update | - **Native mobile app:** High development overhead, less practical for TAs/Instructors performing complex grading tasks<br>- **Desktop application:** Poor accessibility for students |
| **INT-1:** Single Source of Truth | Architect for **future API synchronization with Moodle** | - Moodle is the university's system of record for final grades<br>- Syncing grades avoids double data entry for TAs and Instructors<br>- Centralizes submissions and grades over the long term | - **No Moodle integration:** Creates a competing "source of truth" and requires manual CSV export/import, which is error-prone<br>- **Direct DB access:** Infeasible and highly insecure |
