---
title: Quality requirements
nav_order: 101
layout: default
---

# Quality requirements

## Table of contents

* [Priority matrix](#priority-matrix)
* [Maintainability](#maintainability)
    * [QAS001](#qas001)
* [Security](#security)
    * [QAS002](#qas002)
* [Modifiability](#modifiability)
    * [QAS003](#qas003)
    * [QAS004](#qas004)
* [Deployability](#deployability)
    * [QAS005](#qas005)
* [Performance](#performance)
    * [QAS006](#qas006)

## Priority matrix

| Technical Risk → <br/>Business Importance ↓ | S   | M        | L   |
|---------------------------------------------|-----|----------|-----|
| S                                           | 004 | 001      |     |
| M                                           |     | 002, 005 | 006 |
| L                                           | 003 |          |     |

## Quality Attribute Scenario Priority Rationale

### High Business & High Technical Priority

#### QAS001 - Zero-Downtime Deployment
**Business Priority**: High - Critical for academic continuity during grading periods when any system downtime could disrupt student submissions and instructor grading workflows. The system must remain available during deployment windows to avoid impacting coursework.

**Technical Priority**: High - Requires complex Kubernetes orchestration, rolling update strategies, proper pod lifecycle management, and sophisticated health checking to ensure seamless transitions between versions without service interruption.

### High Business & Medium Technical Priority

#### QAS002 - Personal Data Protection  
**Business Priority**: High - Essential for regulatory compliance and maintaining institutional trust. Student data breaches could have severe legal consequences and damage the university's reputation.

**Technical Priority**: Medium - While security implementation requires careful attention, the patterns for role-based access control, data encryption, and secure API design are well-established in modern web frameworks.

### Medium Business & Medium Technical Priority

#### QAS005 - Automated Health Checks & Self-Healing
**Business Priority**: Medium - Important for reducing operational overhead and ensuring system reliability, but manual intervention remains possible during initial rollout phases.

**Technical Priority**: Medium - Standard Kubernetes patterns for liveness/readiness probes and pod restart policies provide established solutions, though proper configuration requires expertise.

### Medium Business & Low Technical Priority  

#### QAS006 - Backend Response Time Performance
**Business Priority**: Medium - Important for user experience but not critical for core functionality. The 500ms threshold supports efficient workflow without being mission-critical.

**Technical Priority**: Low - Performance optimization through caching, query optimization, and proper indexing follows standard patterns in .NET/PostgreSQL ecosystems.

### Low Business & Low Technical Priority

#### QAS004 - Dynamic Configuration Updates
**Business Priority**: Low - Configuration changes are infrequent in production and can typically be handled through standard deployment processes without requiring dynamic updates.

**Technical Priority**: Low - Simple implementation using established configuration management patterns without complex distributed systems challenges.

### Low Business & Medium Technical Priority

#### QAS003 - Modular Feature Addition
**Business Priority**: Low - While beneficial for long-term maintainability, the initial MVP focuses on core functionality, and feature additions can follow standard development cycles.

**Technical Priority**: Medium - Requires careful microservice design and API contract management, but benefits from the established .NET/React technology stack.

## Maintainability

### QAS001

#### Code Deployment

- Source of Stimulus: Development team
- Stimulus: New deployment
- Environment: Production
- Response: System supports zero-downtime deployment
- Response Measure:
    - Deployment completed within 5 minutes (new image with corresponding release version is created)
    - No service interruption (perform image update using “Rolling Update” strategy, remove old pods only after checking
      availability of new ones)
    - Rollback possible within 5 minutes if needed (using image for previous release)

#### QAST001-1

- Zero-Downtime Deployment Test
- Objective: Verify that a new deployment completes within 5 minutes without causing service interruption or errors for
  ongoing user sessions
- Steps:
    - Initiate a deployment of a new application version
    - Monitor the deployment process in the orchestration tool
- Success Criteria:
    - The deployment process is completed within 5 minutes
    - The orchestration tool's events show no overlap where all pods for the service were unavailable

## Security

### QAS002

#### Personal Data Protection

- Source of Stimulus: Government laws
- Stimulus: Storage of student and staff personal data
- Environment: Local, Staging, Production
- Response: System provide personal data to user itself and authorized staff
- Response Measure:
    - A student cannot see personal info (e.g. grades) about other student
    - No sensitive data stored in logs

#### QAST002-1

- Student Data Isolation Test
- Objective: Verify that a student can only access their own personal information and not that of any other student
- Steps:
    - Create two test student accounts
    - Log in to the system as the first student
    - Try to to access the data of the second student by directly calling the API endpoint
- Success Criteria:
    - The system returns a 403 Forbidden (or 404 Not Found) error, explicitly denying access to the resource

## Modifiability

### QAS003

#### Feature Addition

- Source of Stimulus: Business requirements
- Stimulus: New feature implementation
- Environment: Production
- Response: System supports modular feature addition
- Response Measure:
    - New features can be added without system downtime
    - Existing features remain unaffected

#### QAST003-1

- Modular Feature Deployment Test
- Objective: Verify that a new independent feature (module) can be deployed without causing system downtime or affecting
  existing functionality
- Steps:
    - Deploy a mock service that did not previously exist with some API endpoint
    - Monitor the existing services and overall system health during the deployment
- Success Criteria:
    - The deployment of the new microservice completes without requiring a restart of any existing, unrelated services
    - The API endpoint of the newly deployed service can be successfully called

### QAS004

#### Configuration Management

- Source of Stimulus: Operations team
- Stimulus: Configuration changes
- Environment: Production system
- Response: System supports dynamic configuration updates
- Response Measure:
    - Configuration changes applied within 1 minute
    - Changes propagate to all instances within 30 seconds

#### QAST004-1

- Dynamic Configuration Update Test
- Objective: Verify that a change in a feature flag or application setting propagates to all system instances and takes
  effect within the specified time limits
- Steps:
    - Introduce a new test feature flag and API endpoint for some module that returns the value of that flag
    - After successful deployment, change the flag value in central configuration service
    - Measure the time after which the change is accepted in the configuration service
    - Repeatedly poll the introduced endpoint on all running application instances to check the current value of the
      flag and record the time when the value is changed
- Success Criteria:
    - The updated configuration is available from the source within 1 minute
    - All running application instances report the new configuration value within 30 seconds of it becoming available

## Deployability

### QAS005

#### Deployment Verification

- Source of Stimulus: Deployment process
- Stimulus: Post-deployment checks
- Environment: Production system
- Response: System performs automated health checks
- Response Measure:
    - Health checks are done at least every 10 seconds
    - After 3 failed health checks pod will be marked as unavailable and will be restarted
    - Each module should have at least 1 active pod at any time

#### QAST005-1

- Liveness Probe and Self-Healing Test
- Objective: Verify that the system automatically detects a failing component and restarts it without manual
  intervention, while maintaining service availability
- Steps:
    - Identify a running pod for a specific module
    - Simulate a critical failure inside the pod (e.g., by using kubectl exec to delete a critical process)
    - Monitor the pod's status and the orchestration tool's events
- Success Criteria:
    - The liveness probe fails within a maximum of 30 seconds (3 checks at 10-second intervals)
    - After the third failure, the pod is automatically killed and a new one is started

## Performance

### QAS006

#### Response Time

- Source of Stimulus: User
- Stimulus: Request to backend
- Environment: Production
- Response: System returns requested data
- Response Measure:
    - Results returned within 500ms for 99% of queries

#### QAST006-1

- Backend API Performance Test
- Objective: Verify that 99% of backend requests are served within 500ms under a realistic production load
- Steps:
    - Design a test script that mimics a realistic user workflow
    - Run the test for a sustained period (10 minutes)
    - Collect response time metrics for all backend API calls made during the test
- Success Criteria:
    - The 99th percentile response time for all backend API calls is less than or equal to 500 milliseconds
