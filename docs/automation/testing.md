---
title: Automation
permalink: /automation/
has_children: true
nav_order: 301
layout: default
---

# Testing

## Unit tests

This section outlines the standards and operational procedures for unit testing the backend API.

### File Organization & Naming
To ensure discoverability and consistency, we follow standard .NET conventions:

* **Location:** All tests are located in the `Modules/Grading/Tests` directory.
* **File Naming:** Test files mirror the class being tested with a `Test` suffix (e.g., `CreateOrderCommandTest.cs` tests `CreateOrderCommand.cs`).

### Execution
Tests are executed using the .NET CLI.

**Run all unit tests:**
```bash
dotnet test
```

Generate coverage report: Since we use `coverlet.collector`, we trigger data collection during the test run:
```
dotnet test -c Release --collect:"XPlat Code Coverage" Modules/Grading/Tests
```
This generates a `coverage.cobertura.xml` file in the TestResults directory.

### Coverage Thresholds & Configuration
We enforce code coverage minimums to prevent technical debt.

How to adjust thresholds: Coverage settings are defined in the .runsettings file (or passed via CI pipeline parameters). To adjust the minimum requirement, modify the DataCollectionRunSettings in the configuration file:
```
<Configuration>
  <DataCollectionRunSettings>
    <DataCollectors>
      <DataCollector friendlyName="XPlat Code Coverage">
        <Configuration>
          <Threshold>80</Threshold>
          <ThresholdType>line</ThresholdType>
        </Configuration>
      </DataCollector>
    </DataCollectors>
  </DataCollectionRunSettings>
</Configuration>
```

### Strategy & Rationale

#### 1. Coverage Report Format: Cobertura
We selected **Cobertura (`coverage.cobertura.xml`)** as our output format.
* **Why:** It is the industry standard for coverage data interoperability. It integrates seamlessly with CI/CD pipelines (GitHub Actions/Azure DevOps) and is natively supported by tools like `ReportGenerator` to create visual, human-readable dashboards.

#### 2. Long-Term Standard (80%)
While we aim for high quality in the long run, our "North Star" metric for a stable, mature product is **80% line coverage**. This represents the point where code is reliable without testing trivial boilerplate.

#### 3. MVP Targets (30%)
For the MVP release, we are enforcing a minimum of **30% coverage**.
* **Why:** speed and agility are our primary drivers.
    * **Feature Velocity:** Our focus is on delivering features to users to validate the product. Writing comprehensive tests for every component slows down development.
    * **Code Volatility:** MVP code changes frequently. Maintaining high test coverage on volatile code creates high maintenance overhead (rewriting tests for code that might be deleted next week).
    * **Resource Allocation:** We invest our limited engineering time in building capabilities rather than guarding against edge cases in non-critical paths.

#### 4. Module Selection Strategy
To make our 30% coverage count, we are highly selective about what we test. We ignore boilerplate and focus only on the most fragile or complex areas:

* **High Priority (Included in MVP Tests):**
    * **Complex Domain Logic:** Any calculation, state transition, or business rule that is not a simple data pass-through.
    * **Critical Validators:** Security or data-integrity checks that, if failed, would corrupt the database.
* **Excluded for MVP (To be added later):**
    * **CRUD Handlers:** Simple "Get" or "Create" handlers that just call the database are skipped.
    * **DTOs & Mappers:** Simple object mapping is ignored.
    * **Infrastructure:** We rely on manual testing for database integrations during the MVP phase.


## Quality attribute scenario tests TODO
- Provide a link to that QAST’s section in ./docs/requirements/quality-requirements.md;
- Explain how you automated it, with links to the implementation;
