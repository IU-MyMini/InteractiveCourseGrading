---
title: Tech Stack
parent: Architecture
nav_order: 1
layout: default
---

# Tech Stack

This document outlines the technology stack chosen for the project. The selection prioritizes existing team knowledge, maintainability, and robust open-source ecosystems.

---

## Frontend

The frontend will be a single-page application (SPA) built to be fast, responsive, and maintainable.

### Language

* **TypeScript:** Provides static typing for JavaScript. This catches errors at compile time, improves code quality, and makes large-scale refactoring significantly safer.

### Technologies (Libraries, Frameworks & Tools)

* **React:** A powerful and popular component-based UI library. It allows us to build complex, interactive user interfaces efficiently using reusable components.
* **Vite:** A modern frontend build tool. It offers a significantly faster development experience (near-instant Hot Module Replacement) and optimized production builds.
* **Tailwind CSS:** A utility-first CSS framework. It allows for rapid UI development by styling components directly in the markup, which streamlines the design process and ensures consistency.
* **Axios:** A promise-based HTTP client. It simplifies communication with the backend API, providing an easy-to-use interface for all network requests and handling features like request/response interception.
* **TanStack Query (React Query):** A data-fetching and server-state management library. It declaratively handles data fetching, caching, synchronization, and error handling, which dramatically simplifies component logic.
* **Zod:** A TypeScript-first schema declaration and validation library. It will be used to validate incoming API data and form submissions, ensuring data integrity between the frontend and backend.
* **i18next:** A comprehensive internationalization (i18n) framework. It provides a robust solution for managing translations, enabling the application to support multiple languages.

---

## Backend

The backend will be a .NET-based API designed for performance, scalability, and clean architecture.

### Language

* **C#:** The primary language for the .NET ecosystem. It's a modern, strongly-typed, and performant language ideal for building robust and scalable server-side applications.

### Technologies (Frameworks, Libraries & Tools)

* **ASP.NET Core:** The core web framework for building high-performance web APIs. It provides the foundation for our application's controllers, middleware, dependency injection, and request pipeline.
* **Entity Framework Core (EF Core):** A modern object-relational mapper (O/RM). It simplifies database interaction by allowing us to work with C# objects rather than raw SQL. It will manage data access and schema migrations.
* **MediatR:** An in-process messaging library. It will be used to implement the **CQRS (Command Query Responsibility Segregation)** pattern, creating a clean separation of concerns by decoupling request "callers" from their "handlers."
* **Quartz.NET:** A full-featured job scheduling library. It will be used to manage background tasks, scheduled jobs, and recurring processes (e.g., data cleanup) that need to run outside of the main API request thread.
* **Kiota:** An API client generator. If the backend needs to consume other third-party APIs (defined by an OpenAPI spec), Kiota will be used to automatically generate a strongly-typed C# client.

---

## Database

* **PostgreSQL:** A powerful, open-source object-relational database. It is highly reliable, feature-rich (supporting complex queries, JSONB types, etc.), and well-supported by EF Core. It's a proven choice for production applications requiring data integrity.

---

## Testing

This section details the frameworks and tools used to ensure application reliability through automated testing.

* **xUnit:** The premier open-source unit testing framework for .NET. We use it to write and run automated tests, ensuring individual units of code function correctly and preventing regressions.
* **coverlet.collector:** A cross-platform code coverage framework. It integrates with the build process to measure how much of our code is actually executed by our tests, helping us identify untested logic.
* **Microsoft.NET.Test.Sdk:** The core MSBuild targets and properties required for building .NET test projects. It acts as the bridge that allows our tests and coverage tools to run seamlessly via the standard `dotnet test` command and in CI/CD pipelines.

---

## Static analysis

This section covers tools used to enforce code quality, style consistency, and formatting rules without executing the application.

* **dotnet format:** The built-in code formatter and linter for the .NET SDK. It enforces code style preferences and analyzes code quality based on our `.editorconfig` rules, ensuring a consistent and readable codebase without manual formatting effort.
