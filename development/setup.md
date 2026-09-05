# Development Setup

## Overview

This guide explains the basic environment and steps required to work
on Know Nepal locally.

Know Nepal consists of a Next.js frontend and a Spring Boot backend,
with PostgreSQL used for persistent data.

---

## Prerequisites

Before starting development, make sure the required development tools
are installed:

- Java 21
- Node.js
- npm
- PostgreSQL
- Git

The exact versions and configuration should follow the requirements of
the respective source repositories.

---

## Repository Setup

Clone the required Know Nepal repositories and configure the
development environment according to each repository's instructions.

The source repositories remain the source of truth for:

- Build configuration
- Dependency versions
- Environment variables
- Database configuration
- Runtime configuration

---

## Backend Setup

The backend is built with **Java 21 and Spring Boot**.

Before starting the backend:

1. Configure the required environment variables.
2. Configure access to the required PostgreSQL databases.
3. Ensure database migrations are available.
4. Start the Spring Boot application.

Database schema changes are managed through Flyway migrations.

---

## Frontend Setup

The frontend is built with **Next.js, React, and TypeScript**.

Before starting the frontend:

1. Install the required Node.js dependencies.
2. Configure the required environment variables.
3. Configure the backend API endpoint.
4. Start the Next.js development server.

The frontend communicates with the backend through REST APIs.

---

## Environment Configuration

Environment-specific configuration should be provided through
environment variables rather than committed to the repository.

Do not commit:

- Passwords
- API keys
- JWT secrets
- Database credentials
- Other sensitive configuration

Refer to the source repositories for the current environment
variables required by each application.

---

## Database

Know Nepal uses PostgreSQL for persistent domain data.

Each domain currently has its own database and persistence
configuration.

Development databases should be configured according to the backend
repository's current database configuration.

---

## Running the Application

The frontend and backend are developed as separate applications.

A typical local development environment consists of:

```text
Next.js Frontend
       │
       │ REST API
       ▼
Spring Boot Backend
       │
       ▼
PostgreSQL
