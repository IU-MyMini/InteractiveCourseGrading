# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [0.0.6] - 13.12.2025

### Added
- Student submissions (via files)
- Minor DTO changes

### Fixed
- Updated FileInfo, so that metadata of files can be previewed without downloading

## [0.0.5] - 07.12.2025

### Added
- GET /debug/metrics

## [0.0.4] - 5.12.2025

### Added 
- "Extra" component for ITPD assignments

## [0.0.3] - 28.11.2025

### Fixed
- Assignments ordering in student view

## [0.0.2] - 30.11.2025

### Added

- Assignments ordering in student view

## [0.0.1] - 22.11.2025

### Added
- POST /api/Grading/CourseParticipant
- DELETE /api/Grading/CourseParticipant
- GET /api/Grading/Assignments
- POST /api/Grading/ItpdAssignment
- GET /api/Grading/GroupsWithGrades
- POST /api/Grading/Group
- PUT /api/Grading/Group
- POST /api/Grading/GroupMember
- PUT /api/Grading/Grade
- GET /api/Grading/StudentGrades
- group grading view
- course structure left-panel

## [0.0.0] - 15.11.2025

### Added
- Domain Entities (Course, Assignment, AssignmentComponent, ComponentGrade, Group, CourseParticipant, Teacher, Submission)
- GET /api/Grading/CourseParticipants
- GET /api/Grading/Courses
- GET /api/Grading/Course
- GET /api/Grading/Groups
- courses view
