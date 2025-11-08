---
title: Interview script
parent: ITPD Assignment 2
nav_order: 1
layout: default
---

# Inteview script

## Figma design

- Show current design of student’s and TA’s views

## Discuss Feature Roadmap

### Student Features

- Dashboard to view assignments and grades (individual & group)
- File upload for assignments
- Peer review submission interface

### TA Features

- Simple gradebook view (students vs. assignments)
- Assignment creation
- Submission grading (individual & group scores)
- Group management
- Assignment for peer review

### Instructor Features

- All TA features
- TA management for the course

### System Features

- Integration with University SSO
- Deployment within my.innopolis.university

## Discuss Some Quality Attributes:

- Personal Data Protection - it was mentioned that students should not be able see grades of other students
- We will integrate the new system as a part of my.innopolis.university, so several Quality Attributes refer to safe
  deployment to the existing system (zero-downtime deployment, deployment verification with health-checks)

## Architecture

- Show context diagram
- Frontend: single-page application on TypeScript with React.
- Backend: .NET-based API.
- Database: PostgreSQL
