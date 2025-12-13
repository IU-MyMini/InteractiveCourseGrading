# Project Configuration Management – Self Review

## Summary

Overall, the InteractiveCourseGrading project has a basic configuration management setup: the code, documentation, and issues are under version control and publicly visible. However, several configuration‑management practices are still informal or missing.

The most important areas to improve are:

* **Requirements traceability** – introduce a clear rule to reference issue IDs in commits and pull requests.
* **Decision documentation** – document architectural and process decisions explicitly (e.g. using Architecture Decision Records).
* **Release management** – define a lightweight release process using version tags and links to issues and commits.

Addressing these areas would significantly improve traceability, accountability, and long‑term product quality.

## Traceability

The following traceability paths are currently possible in the project:

1. **Requirement → Implementation (Code)**
   Requirements and tasks are tracked using GitHub Issues. Implementation is performed through Git commits.

   Example path:

   * Requirement: a GitHub Issue in the repository Issues tab
   * Implementation: a commit in the main branch commit history

2. **Implementation → Change History / Release Information**
   Code changes are recorded in commits and summarized at a higher level in the changelog.

   Example path:

   * Commit in the repository history
   * Corresponding entry in `CHANGELOG.md`

3. **Documentation → Implementation**
   High‑level documentation (README and files in `docs/`) describes intended system behavior, which is reflected in the source code.

   Example path:

   * Documentation section in `README.md`
   * Corresponding implementation in the source code

These traceability paths exist but are informal. There is no enforced process ensuring that all links are consistently maintained.

## Review

### Product Context

#### Vision & Scope

Artifacts:

* `README.md`

Assessment:

* **Visibility**: Strong – the project purpose and scope are described in the README.
* **Accessibility**: Strong – documentation is accessible to all stakeholders via the repository.
* **Accountability**: Absent – no explicit owner of the product vision is documented.
* **Traceability**: Absent – the product vision is not traced to specific requirements or implementation.
* **Evolvability**: Present – version control allows the vision and scope to evolve over time.

### Requirements

#### Product Backlog / Issues

Artifacts:

* GitHub Issues, GitHub Projects

Assessment:

* **Visibility**: Present – requirements and tasks are visible as issues.
* **Accessibility**: Strong – issues are accessible to all contributors.
* **Accountability**: Present – issue authorship is visible, and assignees are sometimes used.
* **Traceability**: Strong – issues are consistently referenced in pull requests.
* **Evolvability**: Present – requirements can be refined, updated, or closed over time.

### Planning

#### Sprint Planning & Roadmap

Artifacts:

* GitHub Projects (Product Backlog and Sprint Backlog boards)

Assessment:

* **Visibility**: Present – sprint and product planning are visible through GitHub Projects boards, where issues are organized into backlogs and sprint columns.
* **Accessibility**: Present – planning boards are accessible to project contributors via the repository.
* **Accountability**: Present – issues in the boards can be assigned to specific contributors, making responsibility for planned work visible.
* **Traceability**: Present – planning items are linked to GitHub Issues, which can be (partially) traced to implementation through commits.
* **Evolvability**: Present – backlog items and sprint plans can be updated, reordered, or refined over time as project priorities change.


### Tracking

#### Issue Tracking

Artifacts:

* GitHub Issues

Assessment:

* **Visibility**: Present – progress can be inferred from issue states (open/closed).
* **Accessibility**: Strong – issue tracker is accessible to contributors.
* **Accountability**: Present – assignees are visible when used.
* **Traceability**: Present – some work can be traced from issues to commits informally.
* **Evolvability**: Present – issues, labels, and states can change over time.

---

### Architecture

#### Architectural Documentation

Artifacts:

* `README.md`
* `docs/` directory

Assessment:

* **Visibility**: Present – high‑level architectural information is available.
* **Accessibility**: Strong – architecture documentation is stored in the repository.
* **Accountability**: Absent – architectural decisions do not have documented owners.
* **Traceability**: Absent – architecture is not explicitly linked to requirements or implementation.
* **Evolvability**: Present – architecture documentation can evolve via version control.

### Risks

#### Risk Identification & Management

Artifacts:

* None explicitly documented

Assessment:

* **Visibility**: Absent
* **Accessibility**: Absent
* **Accountability**: Absent
* **Traceability**: Absent
* **Evolvability**: Absent

---

### Implementation

#### Source Code & Version Control

Artifacts:

* GitHub repository
* Commit history

Assessment:

* **Visibility**: Strong – full commit history is visible in GitHub.
* **Accessibility**: Present – access depends on repository permissions.
* **Accountability**: Strong – each commit is associated with a specific author.
* **Traceability**: Present – some commits can be related back to issues, but not consistently.
* **Evolvability**: Strong – version control fully supports code evolution.

### Communication

#### Documentation & Decisions

Artifacts:

* `README.md`
* `docs/` directory
* `CHANGELOG.md`

Assessment:

* **Visibility**: Present – documentation and change history exist.
* **Accessibility**: Strong – documentation is accessible in the repository.
* **Accountability**: Absent – decisions are rarely attributed to individuals or roles.
* **Traceability**: Present – documentation and decisions are linked to code changes, since all the docs are in the repository (docs as a code)
* **Evolvability**: Present – documentation can evolve with the project.

### Releases

#### Versioning & Change History

Artifacts:

* `CHANGELOG.md`

Assessment:

* **Visibility**: Present – changes are summarized in the changelog.
* **Accessibility**: Strong – the changelog is accessible to all stakeholders.
* **Accountability**: Present – releases are explicitly created by someone.
* **Traceability**: Present – changelog entries reflect changes, though links to issues/commits are often missing.
* **Evolvability**: Present – release documentation can evolve over time.
