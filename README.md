<p align="center" style="font-size:32px">
  Interactive Course Grading
</p>
<p align="center">
  <a href="https://my.innopolis.university"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9c/IU_logo.svg/2560px-IU_logo.svg.png" alt="MyMini"></a>
</p>

<p align="center">
    <em>A simplified, integrated LMS for the IT Product Dev course, designed to streamline individual and group grade management.</em>
</p>

## Description

The system will provide a focused LMS layer developed specifically for the needs of the IT Product Dev course at Innopolis University. It directly addresses the pain points of managing complex grading schemes in a shared Google Sheet by providing distinct, role-based views and actions.

The system is not intended to replicate the full feature set of Moodle but to offer a simplified and superior experience for the specific grading, submission, and peer-review tasks of this course. Future integration with the Moodle API is planned to synchronize data and avoid duplicate entry.

## Project Context Diagram

The following diagram illustrates the key stakeholders and external systems that interact with MyMini:

```mermaid
graph TB
    subgraph External Systems
        SSO[University SSO<br/>Identity Provider]
        Moodle[Moodle<br/>Future API Integration]
    end
    
    subgraph Innopolis Platform
        Portal[My.Innopolis Portal<br/>Host Platform]
        App[Our Application]
    end
    
    subgraph Users
        Student[Student]
        TA[Teaching Assistant]
        Instructor[Instructor]
    end
    
    SSO <--> Portal
    Portal <--> App
    App <--> Student
    App <--> TA
    App <--> Instructor
    App -.-> Moodle
    
    style SSO fill:#e1f5fe
    style Moodle fill:#f3e5f5
    style Portal fill:#fff3e0
    style App fill:#e8f5e8
    style Student fill:#ffebee
    style TA fill:#e8eaf6
    style Instructor fill:#f1f8e9
```

**Stakeholders & Systems:**
*   **Students:** Can view assignments, upload submissions, see their own grades, and submit peer reviews.
*   **Teaching Assistants (TAs):** Can create assignments, grade submissions, manage groups, and assign peer reviews.
*   **Instructor:** Has all TA abilities plus the ability to assign TAs to the course.
*   **My.Innopolis Portal:** The primary platform where MyMini will be integrated.
*   **University SSO:** Provides authentication for all users.
*   **Moodle (Future):** An external system for potential future data synchronization.

## Documentation

Documentation for this project can be found [here](https://iu-mymini.github.io/InteractiveCourseGrading/).

---
<p align="center"><em>Innopolis, 2025</em></p>
