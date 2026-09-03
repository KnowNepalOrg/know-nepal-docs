# Frontend Architecture

## Overview

The Know Nepal frontend is built with **Next.js, React, and TypeScript**.

The frontend provides the web interface for exploring Know Nepal's
content and interacting with platform features.

The application communicates with the Spring Boot backend through REST
APIs.

---

## Technology

The frontend uses:

- **Next.js** — Application framework and routing
- **React** — User interface components
- **TypeScript** — Type-safe application development
- **TSX** — React components and pages

---

## Application Structure

The frontend is organized around the application's domain areas and
shared functionality.

Major areas include:

- Geography
- Education
- Destinations
- Culture
- History
- Wildlife
- Healthcare
- Trip Planning

Shared components, utilities, and application logic are reused across
these areas where appropriate.

---

## Application Flow

```text
User
 │
 ▼
Next.js / TypeScript
 │
 │ REST API
 ▼
Spring Boot Backend
 │
 ▼
PostgreSQL
