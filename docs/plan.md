## Project goals

- Eliminate the reliance on cumbersome Google Sheets by providing a single, authoritative, and efficient platform for
  all ITPD course (and beyond) grade management.
- Provide a clear and optimized user interface tailored to the specific needs of each user role (student, technician,
  and teacher), ensuring that they only see the data and actions that are relevant to them.
- Create a flexible system that initially supports specific course workflows, in particular a complex grading system for
  mixed individual/group assignments and a peer review process.
- Create a long-term integrated solution that connects to major university systems (such as SSO, Student portal and
  possibly Moodle) to reduce redundant data entry and become an integral part of the university's digital ecosystem.

## Threshold of success

The project will be considered successful when:

* TAs and the instructor no longer need to use Google Sheets for managing ITPD grades.
* Students can reliably view their individual and group grades without seeing the grades of other students.
* The core workflows — submission upload, peer review assignment, and grading — are fully functional and intuitive for
  all user roles.
* The system is successfully integrated into the `my.innopolis.university` portal using the university's Single Sign-On.

## Feature roadmap

### MVP

* [x] Project Repository & Branch ruleset (Branch protection, peer review)
* [x] Initial Project Documentation & Interview Analysis
* [ ] **Student Features:**
    * [ ] Dashboard to view assignments and grades (individual & group)
    * [ ] File upload for assignments
    * [ ] Peer review submission interface
* [ ] **TA Features:**
    * [ ] Simple gradebook view (students vs. assignments)
    * [ ] Assignment creation
    * [ ] Submission grading (individual & group scores)
    * [ ] Group management
    * [ ] Peer review assignment
* [ ] **Instructor Features:**
    * [ ] All TA features
    * [ ] TA management for the course
* [ ] **System Features:**
    * [ ] Integration with University SSO
    * [ ] Deployment within `my.innopolis.university`

### **Future Enhancements**

* [ ] Moodle API integration for data synchronization
* [ ] Enhanced UI/UX and dashboard analytics
* [ ] Notifications and reminder system

## Progress monitoring

We will monitor our progress toward the MVP using the following methods:

* **Weekly Sprints:** We will operate in one-week sprints. At the beginning of each week, we will hold a planning
  meeting to select tasks from the roadmap, break them into concrete issues, and assign them.
* **GitHub Project Board:** All tasks will be tracked as issues on a GitHub Project (Kanban) board. This will provide a
  clear visual of what is "To Do," "In Progress," and "Done."
* **Roadmap Check-ins:** During our weekly meetings, we will explicitly update the checklist in the "Feature roadmap"
  section to ensure we are staying focused on the core deliverables.
* **Weekly TA/Instructor Demos:** We will aim to demo our progress to a TA or instructor every two weeks. This provides
  a hard deadline and ensures we are building the right features, allowing for course correction based on feedback.

## Contingency plans

If we fall behind schedule or encounter significant blockers, we will implement the following contingency plans,
prioritizing the "Threshold of success" goals above all else.

* **Contingency 1: De-scope SSO Integration.** If the University SSO integration proves to be a major technical or
  administrative bottleneck, we will pivot.
    * **Plan B:** Implement a simple, secure email/password registration system (or use mock authentication) as a
      temporary measure. This allows us to complete and test all core grading workflows. SSO integration will be moved
      to "Future Enhancements."

* **Contingency 2: Simplify Complex Features.** The core workflow is (1) Create Assignment, (2) Submit, (3) Grade.
    * **Plan B:** If "Group management" or "Peer review assignment" logic becomes too complex, we will simplify them.
      For example, instead of a student-facing UI for group formation, we will build a TA-only feature for manually
      assigning students to groups.

* **Contingency 3: Prioritize TA/Instructor Workflow over Student UI.** The primary goal is replacing the TAs' Google
  Sheet.
    * **Plan B:** If time is critical, we will ensure the TA-facing "Assignment creation" and "Grading" features are
      100% functional, even if the student-facing "Dashboard" is very basic (e.g., just a simple list of grades).

* **Contingency 4: Postpone Deployment.**
    * **Plan B:** If deployment within `my.innopolis.university` fails or is delayed, we will deploy the application on
      `stage.my.innopolis.university` for the final demo and code review.