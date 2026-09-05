# Current State

## Overview

Know Nepal is an actively developed digital knowledge platform focused
on structured information about Nepal.

The platform currently combines a Next.js frontend with a Spring Boot
backend and PostgreSQL-based domain data.

The backend follows a modular monolith architecture.

---

## Application Architecture

The current backend is organized into seven main domain modules:

- Geography
- Education
- Destinations
- Culture
- History
- Wildlife
- Healthcare

These domains operate within a single Spring Boot application while
maintaining separate domain responsibilities.

---

## Frontend

The frontend is built with:

- Next.js
- React
- TypeScript

It provides the web interface for exploring Know Nepal's content and
interacting with platform functionality.

The frontend communicates with the backend through REST APIs.

---

## Backend

The backend is built with:

- Java 21
- Spring Boot
- Spring Security
- JWT-based authentication

The backend provides the application and business logic for the
platform and exposes versioned REST APIs using the `/api/v1/` prefix.

---

## Data

Know Nepal uses PostgreSQL for persistent domain data.

Each major domain currently has its own PostgreSQL database and
persistence configuration while remaining part of the same backend
application.

Database schema changes are managed using Flyway migrations.

---

## Caching

The backend uses **Caffeine** for application-level caching.

Caching is used for selected frequently accessed operations to reduce
repeated database queries.

---

## Security

The backend uses Spring Security for authentication and authorization.

JWT-based authentication is used for authenticated API requests.

The backend is the authoritative security boundary for protected
operations.

Security behavior continues to evolve as the project develops.

---

## AI Trip Planning

Know Nepal includes an AI-assisted trip-planning capability.

The trip planner allows users to provide travel preferences and
generate personalized itineraries using Know Nepal's destination and
itinerary data.

The exact implementation and availability of AI functionality may
continue to evolve during development.

---

## Documentation

The project maintains a dedicated public documentation repository,
`know-nepal-docs`.

The documentation covers:

- Project scope
- Architecture
- Domain areas
- Development
- Security
- Architectural decisions
- Contribution guidelines
- Project status

---

## Current Development Status

Know Nepal is in **active development**.

The architecture and functionality continue to evolve as new features
are implemented, tested, and refined.

Some areas of the system may be incomplete or undergoing changes.

The source repositories remain the source of truth for the exact
implementation state.

---

## Known Evolution Areas

The project continues to evolve in areas including:

- Feature development across domain modules
- Security and authorization hardening
- Testing and integration validation
- AI-assisted trip planning
- Documentation
- Deployment and infrastructure

These areas should be treated according to their current
implementation status rather than assumed to be complete.

---

## Related Documentation

- [Project Scope](../about/scope.md)
- [Architecture Overview](../architecture/overview.md)
- [Backend Architecture](../architecture/backend.md)
- [Frontend Architecture](../architecture/frontend.md)
- [Data Architecture](../architecture/data.md)
- [Security Overview](../security/overview.md)
- [Roadmap](roadmap.md)
