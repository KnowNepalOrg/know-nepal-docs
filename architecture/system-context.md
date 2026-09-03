# System Context

## Overview

Know Nepal is a digital knowledge platform focused on Nepal.

The system allows users to explore structured information about Nepal,
including geography, education, destinations, culture, history,
wildlife, and healthcare.

Users can also explore destinations and create personalized
itineraries with Know Nepal AI for their travel planning.

## System Context

```text
                         ┌─────────────────────┐
                         │       Users         │
                         └──────────┬──────────┘
                                    │
                                    │ HTTPS
                                    ▼
                         ┌─────────────────────┐
                         │    Know Nepal       │
                         │      Frontend       │
                         │      Next.js        │
                         └──────────┬──────────┘
                                    │
                                    │ REST API
                                    ▼
                         ┌─────────────────────┐
                         │    Know Nepal       │
                         │      Backend        │
                         │   Spring Boot       │
                         │  Modular Monolith   │
                         └───────┬─────┬───────┘
                                 │     │
                    ┌────────────┘     └─────────────┐
                    ▼                                ▼
          ┌──────────────────┐             ┌──────────────────┐
          │   Domain Data    │             │   Know Nepal AI  │
          │    PostgreSQL    │             │   Trip Planning  │
          └──────────────────┘             └────────┬─────────┘
                                                     │
                                                     ▼
                                            ┌──────────────────┐
                                            │   AI Provider    │
                                            └──────────────────┘
