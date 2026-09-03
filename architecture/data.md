# Data Architecture

## Overview

Know Nepal uses **PostgreSQL** as its primary database system.

The backend separates persistent data by domain. Each domain currently
uses its own PostgreSQL database while remaining part of the same
Spring Boot application.

This provides a clear boundary between domain data without requiring
separate backend services.

---

## Domain Databases

The current backend uses a separate database for each major domain:

- Geography
- Education
- Destinations
- Culture
- History
- Wildlife
- Healthcare

The databases are managed independently at the persistence level while
the domains operate within the same application.

---

## Persistence

Each domain maintains its own persistence configuration.

The backend uses **JPA** for object-relational persistence, with each
domain configured with its own:

- `EntityManagerFactory`
- Transaction manager
- Database connection
- Entity mappings
- Repository layer

This keeps persistence concerns associated with their respective
domains.

---

## Database Migrations

Database schema changes are managed using **Flyway**.

Migration files are maintained separately for each domain, allowing
schema changes to remain associated with the database they belong to.

Flyway manages the application of migrations and keeps track of the
database migration history.

---

## Data Boundaries

Domain data is kept within its respective database boundary.

A domain should primarily access and manage its own persistent data
rather than directly depending on another domain's database.

When functionality requires information from another domain, the
interaction should occur through the appropriate application-level
boundary rather than direct database access.

---

## Data Flow

At a high level, persistent data follows the application flow:

```text
Domain Request
      │
      ▼
Controllers
      │
      ▼
Services
      │
      ▼
Repositories
      │
      ▼
Domain Database
