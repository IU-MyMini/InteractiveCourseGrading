# ITPD Assignment 1

## Interactive IT Product Dev course

### MyMini team

| Name          | Innopolis email               | Github username     | Role               |
|---------------|--------------------------------|---------------------|--------------------|
| Andrei Markov | a.markov@innopolis.university | markovav-official   | Frontend, Lead     |
| Grigorii Fil  | g.fil@innopolis.university    | fil-126             | Backend, DevOps    |
| Timofey Sedov | t.sedov@innopolis.university  | moflotas            | Backend, SRE       |

Innopolis, 2025

---

## Contribution Statements

- **Andrei Markov** - Interview script, Qualitative analysis, Market research
- **Timofey Sedov** - Main documents (report, readme.md)
- **Grigorii Fil** - Qualitative analysis, Market research

All team members participated in review of produced documents.

## Qualitative Analysis Table

[Table](https://docs.google.com/document/d/1kt6N_b5-gGPEHw5qAv6Cka6A8k09a_a9E53ibWKpo0A/edit?usp=sharing)  [Market Research](https://www.figma.com/design/kNRIJP1PPVPJLP5IVdF03v/Interactive-Course-Grading?node-id=0-1&t=sbD4ZrCFcoJQcNRZ-1)

## Github project

[Link](https://github.com/IU-MyMini/InteractiveCourseGrading/)

## Team formation

We formed a team of 3 people, discussed and chose a project which can be potentially integrated with the my.innopolis.university. Combining knowledge of our team, we are capable of creating frontend and backend as well as proper CI-CD integration observability of the project to make it reliable. Andrei would be responsible for the frontend and managing tasks (such as getting permissions to moodle), Grigorii and Timofey are responsible for the backend.

## Setting up GitHub

We already had github accounts, so we did not have to create ones. Then we created the organization as well as a repository with an initial commit. Additionally, we created some rulesets enforced, such as main branch protection and peer review approval requirements before merging to main.

## Short project description

The project will provide integrated LMS for the IT Product Dev course, designed to streamline individual and group grade management. The primary goal is to replace the cumbersome Google Sheets-based grade tracking system for the ITPD course with a lightweight Learning Management System (LMS).

## Existing solutions

We searched for existing grading tools and LMS. Gradescope is the specialized efficiency expert, perfect for large STEM courses where it speeds up grading handwritten exams and code with AI and dynamic rubrics, though it's meant to work alongside a main LMS. For institutions committed to innovative teaching, rbean.io is the pedagogical innovator, built from the ground up to support project-based learning and student reflection, turning the LMS into a lifelong learning portfolio. PowerSchool takes the opposite approach as a comprehensive ecosystem; it's an all-in-one system that ties grades, attendance, and scheduling together in a unified hub for administrators, teachers, and parents, prioritizing district-wide data integration.

Moodle is the open-source powerhouse, offering immense flexibility and a low initial cost, but it requires a strong IT team to build, customize, and maintain the system to fit the institution's exact needs. Finally, Google Spreadsheets is the universal custom tool, a familiar and free spreadsheet that gives individual teachers total control to build their own gradebook, but this comes with significant risks to data security, consistency, and is not practical for institutional use.

### Script for the interview

After researching existing solutions, we created a [script](https://github.com/IU-MyMini/InteractiveCourseGrading/blob/main/docs/sprints/sprint-0/script.md) for our first interview.

### Interview with the Customer

Product should be a simplified LMS for ITPD course.

For now grades are managed in Google Spreadsheet, because in the university official resource (Moodle) it's hard to configure. The main problem faced by the customer is that it is hard to track individual and group progress simultaneously and that TAs need to share it with students, but with limited accessibility.

The new system should support main grading functionality and be simple to use, and also provide a way for students to see their individual scores (students should not see individual grades of other students, which is hard to manage in Google Spreadsheet). Students should be able to: upload submissions, see individual grades, see their group grades, peer review other submissions. TAs can: create assignments, grade it (assign individual and group scores), assign groups for peer review, see all grades in simple format. A teacher has all TA abilities, and can assign TA for the course.

The customer said that it will be great if the product will be integrated in the existing university student portal (my.innopolis.university) and use the university Single Sign-On feature. It also will be great to connect with the Moodle API, so students and teachers do not need to upload data in both systems.

### Initial View of MVP

**Core Vision:** A lightweight, integrated LMS layer that simplifies grade management for ITPD courses, eliminating the reliance on Google Sheets. The goal is not to replicate Moodle's full feature set, but to create a focused experience for the specific problems of tracking individual/group work and sharing these information with students.

**Initial functionality:**

#### Student:

- **View:** A dashboard showing:
  - List of assignments.
  - Their own individual grades for each assignment.
  - Their group’s grade for group assignments.
  - Assignments that should be reviewed.
- **Actions:**
  - Upload a submission file for a given assignment.
  - Submit a peer review for a given assignment.

#### TA:

- **View:** A simple gradebook table
  - Rows: Students (grouped by teams).
  - Columns: Assignments (with separate grading elements including individual scores).
- **Actions:**
  - Create a new assignment.
  - Grade submissions.
  - Assign students to groups.
  - Assign groups to review other groups.

#### Course Instructor:

- Has all TA abilities.
- **Additional Action:** assign TAs for the course.

#### Tech Integrations:

- **MyUniversity portal (my.innopolis.university):** software will be implemented as part of the existing ecosystem, allowing for integration with other services.
- **Authentication:** Single Sign-On provided by the university will be used, so users do not have to register in the system.

**Next steps:** After completing the main features, integration with Moodle could be implemented, allowing for a simplified grading process for TAs without the need to update grades in two places. Some metrics or charts could be added to provide dashboard analytics.

**Docs and README.md**

After conducting an interview, we finalized our sprint docs and polished README.md.
