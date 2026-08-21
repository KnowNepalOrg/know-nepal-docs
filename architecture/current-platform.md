# Know Nepal Current Platform Architecture

This document describes the current architecture of the Know Nepal platform.

It focuses on the application as it exists today rather than historical architectural designs or future proposals.

> **Current architecture:** Know Nepal currently uses a modular monolith architecture for its backend. The frontend and backend are maintained within the `know-nepal-platform` repository.

---

## Platform Overview

The Know Nepal platform consists of a frontend application and a backend application supported by database and infrastructure components.

At a high level:

```text
                         Know Nepal Platform
                                │
                 ┌──────────────┴──────────────┐
                 │                             │
                 ▼                             ▼
             Frontend                       Backend
                 │                             │
        Next.js / Typescript                Spring Boot / Java
                                               │
                                  ┌────────────┼────────────┐
                                  │            │            │
                                  ▼            ▼            ▼
                              Geography     History      Culture
                                  │            │            │
                                  ├────────────┼────────────┤
                                  │            │            │
                                  ▼            ▼            ▼
                           Destinations    Wildlife    Education
                                               │
                                               ▼
                                          Healthcare
                                               │
                                               ▼
                                           PostgreSQL
```

The seven knowledge domains are implemented as modules within the backend application.

They are **not currently deployed as seven independent backend services**.

---

## Repository Structure

The main application is maintained in the `know-nepal-platform` repository.

The simplified organization is:

```text
KnowNepal Organization
│
├── know-nepal-platform
│   │
│   ├── know-nepal-frontend
│   │
│   └── know-nepal-monolith
│
├── know-nepal-api
│
├── know-nepal-infrastructure
│
├── know-nepal-docs
│
└── .github
```

Each repository has a different responsibility.

---

## `know-nepal-platform`

This is the main application repository.

It contains the frontend and backend application code.

```text
know-nepal-platform/
│
├── know-nepal-frontend/
│
└── know-nepal-monolith/
```

The platform repository is therefore the primary source for the current application implementation.

---

## `know-nepal-frontend`

This contains the frontend application.

The frontend is responsible for:

- User interface
- Navigation
- Page rendering
- User interactions
- Communicating with backend APIs
- Presenting information from the different knowledge domains

The frontend uses the backend API rather than directly accessing the database.

---

## `know-nepal-monolith`

This contains the current backend application.

The backend is implemented using Java and Spring Boot.

It contains the major knowledge domains as internal modules:

```text
know-nepal-monolith/
│
├── Geography
├── History
├── Culture
├── Destinations
├── Wildlife
├── Education
└── Healthcare
```

The backend is deployed as a single application rather than as one independently deployed application per domain.

---

# Frontend Architecture

The frontend provides the user-facing layer of the platform.

A simplified request flow is:

```text
User
 │
 ▼
Next.js Application
 │
 │ HTTP / REST
 ▼
Spring Boot Backend
 │
 ▼
Relevant Domain Module
 │
 ▼
Database
```

The frontend does not directly access PostgreSQL.

This keeps database access and domain logic within the backend.

---

# Backend Architecture

The backend is a modular monolith.

This means:

> The application is deployed as one backend application while its internal code is organized into clear domain boundaries.

The current domain structure is:

```text
Spring Boot Application
│
├── Geography Module
├── History Module
├── Culture Module
├── Destinations Module
├── Wildlife Module
├── Education Module
└── Healthcare Module
```

Each module is responsible for its own domain.

---

# Domain Modules

## Geography

The Geography module handles geographical information related to Nepal.

Examples include:

- Provinces
- Districts
- Municipalities
- Wards
- Geographic relationships
- Emergency contacts

---

## History

The History module handles structured historical information.

Examples include:

- Historical eras
- Historical figures
- Dynasties
- Historical events

---

## Culture

The Culture module handles cultural information.

Examples include:

- Languages
- Ethnic groups
- Festivals
- Art forms
- Traditional attire
- Culture media

---

## Destinations

The Destinations module handles destination and travel-related information.

Examples include:

- Tourist destinations
- Destination categories
- Destination tags
- Trekking routes
- Destination highlights
- Destination reviews
- Destination media
- Destination fees
- Itineraries
- Nearby destinations
- Destination weather

---

## Wildlife

The Wildlife module handles wildlife and biodiversity information.

Examples include:

- Wildlife species
- Flora species
- National parks
- Lakes
- Wildlife media

---

## Education

The Education module handles education-related information.

Examples include:

- Schools
- Colleges
- Universities
- Programs
- Exam boards
- Entrance examinations
- Scholarships
- Teacher profiles
- Academic calendars
- Fee breakdowns
- Rankings

---

## Healthcare

The Healthcare module handles healthcare-related information.

Examples include:

- Hospitals
- Specialties
- Hospital-specialty relationships

The exact scope of this domain may evolve as the platform develops.

---

# Domain Boundaries

The seven domains are logically separated even though they run inside the same backend application.

The intended responsibility is:

```text
Geography
    └── Geographic information

History
    └── Historical information

Culture
    └── Cultural information

Destinations
    └── Destination information

Wildlife
    └── Wildlife and biodiversity

Education
    └── Education information

Healthcare
    └── Healthcare information
```

A domain should avoid taking ownership of functionality that belongs to another domain.

Cross-domain relationships should be introduced deliberately.

---

# Backend Layer Structure

The backend uses a layered/domain-oriented structure.

A typical domain may contain components such as:

```text
Domain Module
│
├── Controller
├── Service
├── Repository
├── Model / Entity
├── DTO
├── Mapper
├── Specification
├── Exception
└── Validation / Supporting Components
```

Not every domain is required to contain exactly the same components.

The structure should reflect the actual requirements of the domain.

---

# Persistence

PostgreSQL is used as the primary persistent database.

The backend uses JPA/Hibernate for object-relational persistence.

Database schema changes are managed using Flyway migrations.

The migration structure is organized by domain:

```text
db/migration/
│
├── culture/
├── destinations/
├── education/
├── geography/
├── healthcare/
├── history/
└── wildlife/
```

This allows database evolution to remain aligned with domain boundaries.

---

# Domain Persistence Boundaries

The current backend contains domain-specific persistence configuration.

A simplified representation is:

```text
                    Spring Boot Backend
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼
      Geography        Education       Destinations
      Persistence      Persistence      Persistence
          │                │                │
          └────────────────┼────────────────┘
                           │
                           ▼
                       PostgreSQL
```

The exact database and schema topology is an infrastructure and deployment concern.

---

# API Communication

The frontend communicates with the backend through HTTP APIs.

The general communication model is:

```text
Frontend
    │
    │ HTTP / REST
    ▼
Spring Boot Controller
    │
    ▼
Application / Domain Service
    │
    ▼
Repository
    │
    ▼
PostgreSQL
```

The frontend does not communicate directly with individual domain databases.

The backend owns domain logic and database access.

---

# Authentication

The backend includes JWT-based authentication.

The general authentication flow is:

```text
User
 │
 ▼
Authentication Endpoint
 │
 ▼
Credentials Validation
 │
 ▼
JWT
 │
 ▼
Authenticated API Request
```

The frontend contains corresponding authentication handling for protected application areas.

Authentication and authorization are separate concerns and should remain clearly distinguished.

---

# Caching

The backend uses Caffeine for application-level caching.

The cache is local to the running application process.

Therefore:

```text
Application Instance
       │
       └── Local Caffeine Cache
```

The cache should not be considered a shared distributed data store.

Caching is primarily used to reduce unnecessary repeated work and improve application performance.

---

# API Documentation

The backend provides API documentation support through OpenAPI / Springdoc.

API-level documentation is maintained separately from the high-level platform architecture.

The `know-nepal-api` repository is also maintained within the organization.

Its exact role should be documented from the repository itself rather than assumed by this document.

---

# Infrastructure Relationship

The application and infrastructure are maintained separately.

The relationship can be represented as:

```text
know-nepal-platform
        │
        ├── Frontend
        │
        └── Backend
                │
                ▼
     know-nepal-infrastructure
                │
                ├── Deployment
                ├── Hosting
                ├── Database infrastructure
                └── Operational configuration
```

The infrastructure repository is responsible for infrastructure-specific implementation.

This documentation repository describes the application architecture at a higher level.

---

# Why Modular Monolith?

The current architecture intentionally keeps the seven domains inside a single backend application.

This provides:

- Clear domain boundaries
- One backend deployment unit
- Lower operational complexity
- Easier local development
- Easier debugging
- Lower distributed-system overhead
- Domain-specific persistence boundaries
- A possible future path toward service extraction

The goal is not to create as many services as possible.

The goal is to maintain useful boundaries while keeping the system understandable and maintainable.

---

# Future Service Extraction

A domain may eventually be extracted into an independently deployed service if there is a concrete reason.

Potential reasons could include:

- Independent scaling requirements
- Independent deployment requirements
- Strong operational boundaries
- Different infrastructure requirements
- Significant workload differences
- Organizational ownership requirements

However, extraction should be driven by an actual requirement rather than architectural fashion.

Until such a change is implemented, the domain remains part of the modular monolith.

---

# Historical Architecture

Know Nepal previously explored a microservices-oriented architecture.

That architecture represented domains as separate services behind an API Gateway.

That design is **historical**.

The current platform does not use the previous service-per-domain deployment model.

Historical infrastructure documentation may still exist in the infrastructure repository, but it should be clearly identified as historical when it describes the previous architecture.

---

# Source of Truth

For the current platform:

> **The implemented application source code is the primary source of truth.**

Documentation should describe the implementation accurately and should be updated when significant architectural changes are introduced.

When a feature is not implemented, it should not be documented as an implemented capability.

Documentation should distinguish between:

- Implemented
- Partial
- Planned
- Proposed
- Historical
- Deprecated
- Unknown

---

# Architecture Evolution

Know Nepal is an actively developing platform.

The architecture may evolve as:

- New requirements appear
- Domains become more mature
- Performance requirements become clearer
- Infrastructure requirements change
- Contributors join the project
- Production experience provides new information

Significant architectural changes should be recorded so that future contributors can understand not only **what changed**, but also **why it changed**.

---

# Summary

The current Know Nepal platform can be summarized as:

```text
                    KNOW NEPAL
                        │
              ┌─────────┴─────────┐
              │                   │
              ▼                   ▼
          Frontend             Backend
       Next.js / Typescript      Spring Boot / Java
                                  │
             ┌───────────┬────────┼───────────┐
             │           │        │           │
             ▼           ▼        ▼           ▼
         Geography    History   Culture   Destinations
             │           │        │           │
             └───────────┼────────┼───────────┘
                         │        │
                    ┌────┴────────┴────┐
                    ▼                 ▼
                 Wildlife          Education
                    │
                    ▼
                Healthcare
                    │
                    ▼
                PostgreSQL
```

**Architecture style:** Modular monolith

**Frontend:** Next.js / Typescript

**Backend:** Java / Spring Boot

**Database:** PostgreSQL

**Migrations:** Flyway

**Authentication:** JWT-based

**Caching:** Caffeine

**Current domain modules:** Geography, History, Culture, Destinations, Wildlife, Education, Healthcare
