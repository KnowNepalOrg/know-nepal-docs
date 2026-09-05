# Security Overview

## Overview

Security in Know Nepal is primarily enforced by the Spring Boot
backend.

The backend uses **Spring Security** and **JWT-based authentication**
to control access to protected application functionality.

The frontend may provide authentication-related user interfaces and
client-side behavior, but backend security remains the authoritative
enforcement layer.

---

## Security Responsibilities

The security layer is responsible for:

- Authentication
- Authorization
- Processing authenticated requests
- Protecting restricted operations
- Managing access based on authenticated identity and permissions

Security decisions should be enforced on the server rather than
relying solely on frontend restrictions.

---

## Authentication

Know Nepal uses **JSON Web Tokens (JWT)** for authentication.

An authenticated request can include a JWT that is processed by the
backend security layer.

The authentication mechanism establishes the identity associated with
the request before protected application functionality is executed.

Detailed authentication behavior is documented in:

- [Authentication](authentication.md)

---

## Authorization

Authentication and authorization are separate concerns.

**Authentication** determines who is making a request.

**Authorization** determines whether that authenticated identity is
allowed to perform the requested operation.

Protected operations should therefore be enforced by the backend rather
than relying only on frontend route protection.

---

## Public and Protected Access

Not every Know Nepal endpoint requires authentication.

Public functionality may be accessible without an authenticated
session, while operations that modify or manage protected data require
appropriate authorization.

The exact access rules are defined by the backend security
configuration and should be treated as the source of truth.

---

## Frontend Security

The frontend can restrict access to user interfaces and routes, but
frontend restrictions are not a replacement for backend authorization.

A user should not be able to perform a protected operation simply by
bypassing a frontend restriction.

The backend must independently validate authentication and
authorization for protected operations.

---

## Secrets and Sensitive Configuration

Sensitive security configuration must not be committed to public
repositories.

This includes:

- JWT signing secrets
- Passwords
- Database credentials
- API keys
- Private tokens
- Other authentication credentials

Secrets should be supplied through the appropriate environment or
secret-management mechanism.

---

## Security Principles

Know Nepal follows these general security principles:

- Enforce authorization on the backend.
- Keep authentication separate from authorization.
- Do not rely on frontend access control alone.
- Keep secrets outside source control.
- Protect data-modifying operations appropriately.
- Prefer least-privilege access.
- Keep security behavior consistent across API endpoints.
- Document significant security changes.

---

## Source of Truth

The backend security configuration is the source of truth for the
currently enforced security behavior.

This documentation describes the security architecture and principles;
it should be updated whenever the actual security model changes.

---

## Related Documentation

- [Authentication](authentication.md)
- [Backend Architecture](../architecture/backend.md)
- [Request Lifecycle](../architecture/request-lifecycle.md)
- [Development Conventions](../development/conventions.md)
