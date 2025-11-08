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

![Sequence diagram](assets/sequence-diagram-qast002-1.png)

#### QAST005-1

![Sequence diagram](assets/sequence-diagram-qast005-1.png)
