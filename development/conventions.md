# Development Conventions

## Overview

Development conventions help keep the Know Nepal codebase consistent,
readable, and maintainable as the project grows.

Conventions should support the existing architecture and avoid adding
unnecessary complexity.

The source repositories remain the source of truth for framework-specific
configuration, formatting rules, and tooling.

---

## General Principles

Development should follow these general principles:

- Prefer clear and readable code.
- Keep responsibilities separated.
- Follow the existing project structure before introducing new patterns.
- Prefer simple solutions over unnecessary abstraction.
- Avoid duplicating existing functionality.
- Keep changes focused on the problem being solved.
- Remove unused code and configuration when appropriate.
- Do not introduce infrastructure or dependencies without a clear need.

---

## Backend Conventions

The backend is built with **Java 21 and Spring Boot**.

Backend code should maintain clear separation between application
responsibilities.

In general:

- Controllers handle HTTP concerns.
- Services handle application and business logic.
- Repositories handle persistence.
- Domain-specific functionality remains within its appropriate module.
- Shared functionality should only be extracted when it is genuinely
  reusable.
- Database access should remain within the appropriate domain boundary.

New backend code should follow the patterns already established in the
existing modules rather than introducing a different architectural
pattern without a clear reason.

---

## Frontend Conventions

The frontend is built with **Next.js, React, and TypeScript**.

Frontend development should:

- Use TypeScript for application code.
- Prefer reusable React components where appropriate.
- Keep presentation concerns separate from business logic.
- Keep API communication organized and consistent.
- Follow the existing application structure.
- Avoid unnecessary duplication between pages and components.

Components should remain focused on a clear responsibility.

---

## API Conventions

Backend APIs use the `/api/v1/` prefix for versioned application
endpoints.

API changes should maintain consistency with existing:

- Endpoint naming
- HTTP methods
- Request structures
- Response structures
- Validation behavior
- Error handling

Changes to API behavior should be reflected in the relevant API
documentation when necessary.

---

## Database Conventions

Database changes should be managed through **Flyway migrations**.

Developers should:

- Use migrations for schema changes.
- Keep migrations associated with the appropriate domain.
- Avoid making undocumented manual schema changes.
- Keep domain data within its appropriate database boundary.
- Avoid direct cross-domain database access.

---

## Configuration and Secrets

Environment-specific configuration should be provided through
environment variables or the appropriate configuration mechanism.

The following must not be committed to public repositories:

- Passwords
- API keys
- JWT secrets
- Database credentials
- Private tokens
- Other sensitive configuration

Example or placeholder values should be used when configuration needs
to be documented publicly.

---

## Documentation Conventions

Documentation should:

- Describe the system as it currently exists.
- Use clear and direct technical language.
- Avoid unnecessary marketing language.
- Clearly distinguish implemented functionality from planned work.
- Avoid duplicating source code or configuration.
- Link to related documentation where useful.
- Be updated when significant architectural behavior changes.

Documentation should remain useful to both current contributors and
future maintainers.

---

## Git and Changes

Changes should be kept focused and understandable.

Commit messages should clearly describe the purpose of the change.

Examples:

```text
docs: update backend architecture
docs: add testing documentation
feat: add destination filtering
fix: handle invalid trip planner requests
