# Backend Architecture

## Overview

The Know Nepal backend is built with **Java 21 and Spring Boot**.

It follows a **modular monolith** architecture. The domain areas are
organized as separate modules within a single Spring Boot application
rather than as independently deployed microservices.

This structure provides clear separation between domains while keeping
the deployment and operational model simple.

---

## Backend Structure

The backend is organized around seven main domain modules:

- Geography
- Education
- Destinations
- Culture
- History
- Wildlife
- Healthcare

Each domain contains its own application logic and persistence
configuration while running within the same backend application.

### Domain Modules

#### Geography

Handles Nepal's geographic and administrative information, including
provinces, districts, municipalities, wards, and related data.

#### Education

Handles education-related information, including schools, colleges,
universities, programs, and related data.

#### Destinations

Handles tourism and travel-related information, including destinations,
itineraries, trekking routes, fees, media, reviews, weather, and
related data.

#### Culture

Handles cultural information, including festivals, languages, ethnic
groups, art forms, traditional attire, and related data.

#### History

Handles historical information, including historical figures,
dynasties, eras, events, and related data.

#### Wildlife

Handles wildlife and natural-resource information, including national
parks, species, flora, lakes, and related data.

#### Healthcare

Handles healthcare information, including hospitals, specialties, and
hospital-specialty relationships.

---

## Request Flow

A typical request passes through the backend security and application
layers:

```text
HTTP Request
     │
     ▼
Spring Security
     │
     ▼
Controller
     │
     ▼
Service
     │
     ▼
Repository
     │
     ▼
Domain Database
```

- **Spring Security** handles the security layer for incoming requests.
- **Controller** handles HTTP requests and responses.
- **Service** contains application and business logic.
- **Repository** handles persistence operations.

---

## Persistence

The backend uses **PostgreSQL** for persistent data.

Each domain currently uses a separate PostgreSQL database. This keeps
domain data separated while allowing all domains to operate within the
same Spring Boot application.

Each domain also maintains its own persistence configuration, including
its JPA `EntityManagerFactory` and transaction manager.

---

## Database Migrations

Database schema changes are managed using **Flyway**.

Each domain maintains its own migration files and migration history,
keeping database changes associated with their respective domain.

---

## Caching

The backend uses **Caffeine** for application-level caching.

Caching is used for selected frequently accessed data to reduce
repeated database queries and improve application performance.

---

## Authentication and Security

The backend uses **Spring Security** with **JWT-based authentication**.

Authentication and authorization are separate concerns:

- **Authentication** establishes the identity associated with a request.
- **Authorization** determines whether that identity is permitted to
  perform a specific operation.

Detailed security architecture and authorization rules are documented
separately.

See:

- [Security Overview](../security/overview.md)
- [Authentication](../security/authentication.md)

---

## API Layer

The backend exposes **REST APIs** consumed by the Know Nepal frontend.

Application endpoints use the `/api/v1/` prefix for API versioning.

Controllers provide the HTTP interface for the domain modules and
delegate application logic to the service layer.

Detailed endpoint definitions are maintained separately in the API
documentation.

---

## AI Trip Planning

Know Nepal includes an **AI-assisted trip-planning capability** that
allows users to create personalized travel itineraries.

The capability operates within the existing backend architecture and
works with destination and itinerary-related functionality.

Detailed AI architecture is documented separately.

---

## Architectural Evolution

Know Nepal previously explored a **microservices architecture**.

The current backend uses a **modular monolith** to maintain domain
separation without requiring each domain to be independently deployed.

This provides:

- Clear domain boundaries
- Simpler deployment
- Lower infrastructure requirements
- Simpler local development
- Reduced service-to-service communication
- A practical foundation for future evolution

The architecture may evolve in the future if there is a clear technical
requirement to extract one or more domains into independent services.

---

## Backend Principles

The backend follows these general principles:

- Keep domain responsibilities clearly separated.
- Keep business logic within the service layer.
- Keep controllers focused on HTTP concerns.
- Keep persistence logic within the appropriate domain.
- Minimize unnecessary cross-domain coupling.
- Prefer simple and maintainable solutions.
- Avoid distributed infrastructure without a clear technical need.
- Keep architectural decisions aligned with the current system
  requirements.

---

## Related Documentation

- [Architecture Overview](overview.md)
- [System Context](system-context.md)
- [Data Architecture](data.md)
- [Request Lifecycle](request-lifecycle.md)
- [Security Overview](../security/overview.md)
- [Authentication](../security/authentication.md)
