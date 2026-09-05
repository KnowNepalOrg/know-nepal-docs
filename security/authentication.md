# Authentication

## Overview

Know Nepal uses **JWT-based authentication** through **Spring
Security**.

Authentication allows the backend to establish the identity associated
with an incoming request.

---

## Authentication Flow

A simplified authentication flow is:

```text
User
 │
 ▼
Frontend
 │
 │ Authentication Request
 ▼
Spring Boot Backend
 │
 ▼
Authentication
 │
 ▼
JWT
 │
 ▼
Authenticated API Request
