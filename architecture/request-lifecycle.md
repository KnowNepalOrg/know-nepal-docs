# Request Lifecycle

## Overview

A request to Know Nepal typically passes through the frontend, backend
security layer, application layers, and the appropriate domain
database.

The general flow is:

```text
User
 │
 ▼
Next.js Frontend
 │
 │ HTTP / REST
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
 │
 ▼
Response
```

---

## Request Flow

### 1. User Interaction

A user interacts with the Know Nepal frontend through the web
application.

The frontend sends an HTTP request when data needs to be retrieved or
an operation needs to be performed.

### 2. API Request

The request is sent from the Next.js frontend to the Spring Boot
backend through the REST API.

API endpoints use the `/api/v1/` prefix.

### 3. Security

The request passes through the backend security layer.

Spring Security handles authentication and the security context
associated with the request.

For protected operations, authorization determines whether the
authenticated user is permitted to perform the requested operation.

### 4. Controller

The request reaches the appropriate REST controller.

The controller handles HTTP-specific concerns such as:

- Request parameters
- Request bodies
- Validation
- HTTP responses

The controller delegates application logic to the service layer.

### 5. Service

The service layer performs the required application and business logic.

It coordinates the operation and interacts with the appropriate
repository when persistent data is required.

### 6. Repository

The repository layer handles persistence operations.

The repository interacts with the PostgreSQL database belonging to the
relevant domain.

### 7. Response

The result is returned through the same application layers and sent
back to the frontend as an HTTP response.

The frontend then uses the response to update the user interface.

---

## Read and Write Operations

The general lifecycle applies to both read and write operations.

For a read operation:

```text
Request
  ↓
Security
  ↓
Controller
  ↓
Service
  ↓
Repository
  ↓
Database
  ↓
Response
```

For a write operation:

```text
Request
  ↓
Security
  ↓
Controller
  ↓
Service
  ↓
Repository
  ↓
Database Update
  ↓
Response
```

The main difference is the operation performed by the service and
repository layers.

---

## Error Handling

Errors encountered during request processing are handled by the
backend and returned as appropriate HTTP responses.

The frontend uses these responses to present the relevant result or
error state to the user.

---

## Architectural Boundary

The request lifecycle maintains a clear separation of responsibilities:

- **Frontend** — User interface and client-side behavior
- **Security** — Authentication and authorization
- **Controller** — HTTP interface
- **Service** — Application and business logic
- **Repository** — Persistence
- **Database** — Persistent domain data

This separation makes the request path easier to understand,
maintain, and troubleshoot.

---

## Related Documentation

- [Architecture Overview](overview.md)
- [Backend Architecture](backend.md)
- [Frontend Architecture](frontend.md)
- [Data Architecture](data.md)
- [Security Overview](../security/overview.md)
