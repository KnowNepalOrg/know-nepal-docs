# Error Handling

## Purpose

This document describes error-handling principles for the Know Nepal platform.

Consistent error handling helps the frontend communicate failures clearly, helps developers diagnose problems, and prevents sensitive implementation details from being exposed.

## Scope

Error handling applies to:

- Frontend application errors
- Backend REST API errors
- Request validation failures
- Authentication and authorization failures
- Database and persistence failures
- External service and AI integration failures

## General Principles

- Return appropriate HTTP status codes for API requests.
- Provide clear and useful error messages.
- Validate incoming requests before processing them.
- Keep internal exception details out of public API responses.
- Log relevant technical details for troubleshooting.
- Handle expected failures without unnecessarily interrupting the user.
- Avoid exposing secrets, credentials, tokens, or sensitive data in error messages and logs.

## HTTP Status Codes

The backend should use HTTP status codes consistently.

| Status | Meaning | Typical Use |
|---|---|---|
| `400 Bad Request` | Invalid request | Malformed input or validation failure |
| `401 Unauthorized` | Authentication required or invalid | Missing or invalid authentication credentials |
| `403 Forbidden` | Access denied | Authenticated request lacks required permission |
| `404 Not Found` | Resource not found | Requested resource does not exist |
| `409 Conflict` | Request conflicts with current state | Duplicate or conflicting operation |
| `429 Too Many Requests` | Request limit exceeded | Rate limiting, where implemented |
| `500 Internal Server Error` | Unexpected server failure | Unhandled backend errors |
| `502 Bad Gateway` | Upstream service failure | Invalid response from an upstream service, where applicable |
| `503 Service Unavailable` | Service temporarily unavailable | Temporary service or dependency outage |

The status code should reflect the actual failure. Not every error requires a unique status code, and these examples do not imply that every case is currently implemented.

## Backend Error Handling

The backend is built with Java and Spring Boot.

Backend error handling should:

- Validate request data before performing operations.
- Return appropriate HTTP status codes.
- Use consistent response structures where practical.
- Handle known exceptions explicitly.
- Provide a safe fallback for unexpected exceptions.
- Log diagnostic information without exposing sensitive data.
- Avoid returning stack traces or internal implementation details to clients.

A shared exception-handling mechanism may be used to keep REST API responses consistent across domain modules.

## Frontend Error Handling

The frontend is built with Next.js, React, and TypeScript.

Frontend error handling should:

- Display understandable messages when requests fail.
- Distinguish validation errors from authentication, authorization, and server failures.
- Provide loading, success, empty, and error states where appropriate.
- Avoid displaying raw stack traces or internal server responses.
- Allow users to retry operations when retrying is safe.
- Prevent repeated submissions when an operation is still processing.

Error messages should explain what the user can do next when that information is available.

## Authentication and Authorization Errors

Authentication and authorization failures should be handled separately.

- `401 Unauthorized`: the request lacks valid authentication credentials.
- `403 Forbidden`: the request is not permitted under the applicable access rules.

The frontend should respond appropriately without assuming that hiding a button or page provides security. Access control must be enforced by the backend.

## External Service Failures

Features that depend on external services, including AI-assisted trip planning, may encounter timeouts, unavailable services, or invalid responses.

Handling should:

- Return a controlled error response.
- Avoid exposing provider credentials or internal service details.
- Provide a useful message to the user.
- Use retries only when appropriate and safe.
- Avoid presenting incomplete results as successful output.

## Logging and Troubleshooting

Logs should contain enough information to investigate failures without recording unnecessary sensitive information.

Where appropriate, logs may include:

- Error category
- Timestamp
- Request or correlation identifier
- Relevant operation or endpoint
- Exception details for internal diagnosis

Credentials, authentication tokens, and other sensitive values must not be logged.

## Testing

Error-handling behavior should be tested where applicable.

Tests may cover:

- Invalid request data
- Missing or invalid authentication
- Insufficient permissions
- Missing resources
- Database failures
- External service failures
- Unexpected exceptions
- Frontend error states and recovery behavior

Tests should verify both the returned response and any important security requirements.

## Implementation Status

This document defines error-handling principles and recommended practices. It does not claim that every listed behavior is already implemented throughout the platform.

The actual implementation should be verified against the current frontend and backend source code.

## Related Documentation

- [Backend Architecture](backend.md)
- [Frontend Architecture](frontend.md)
- [Request Lifecycle](request-lifecycle.md)
- [Security Overview](../security/overview.md)
- [Testing](../development/testing.md)
