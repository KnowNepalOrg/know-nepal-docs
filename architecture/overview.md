# Architecture Overview

## Overview

Know Nepal is currently structured as a **modular monolith**.

The system consists of a Next.js frontend and a Spring Boot backend.
The backend is organized into separate domain modules while running
as a single application.

This architecture keeps the system relatively simple to develop,
test, and deploy while maintaining clear boundaries between domains.

## High-Level Architecture

```text
                         ┌─────────────────────┐
                         │        Users        │
                         └──────────┬──────────┘
                                    │
                                  HTTPS
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │      Next.js        │
                         │      Frontend       │
                         └──────────┬──────────┘
                                    │
                                 REST API
                                    │
                                    ▼
              ┌──────────────────────────────────────────┐
              │           Spring Boot Backend             │
              │            Modular Monolith               │
              │                                          │
              │  ┌────────────┐    ┌────────────┐        │
              │  │ Geography  │    │ Education  │        │
              │  └────────────┘    └────────────┘        │
              │                                          │
              │  ┌────────────┐    ┌────────────┐        │
              │  │  Culture   │    │Destinations│        │
              │  └────────────┘    └────────────┘        │
              │                                          │
              │  ┌────────────┐    ┌────────────┐        │
              │  │  Wildlife  │    │ Healthcare │        │
              │  └────────────┘    └────────────┘        │
              │                                          │
              │             ┌────────────┐               │
              │             │  History   │               │
              │             └────────────┘               │
              └────────────────────┬─────────────────────┘
                                   │
                                   ▼
                         ┌─────────────────────┐
                         │     PostgreSQL      │
                         │     Domain Data     │
                         └─────────────────────┘
