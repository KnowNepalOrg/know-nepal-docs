# Healthcare

## Overview

The **Healthcare** domain provides structured information about
healthcare services across Nepal.

It allows users to explore hospitals, medical specialties, and related
healthcare information.

---

## Domain Scope

The Healthcare domain covers:

- Hospitals
- Medical specialties
- Healthcare services
- Hospital-specialty relationships

---

## Data

Healthcare data is stored within the Healthcare domain's PostgreSQL
database.

The domain maintains its own persistence boundary within the Know Nepal
backend.

---

## Backend

The Healthcare domain is implemented as a module within the Spring Boot
modular monolith.

Its application responsibilities remain within the Healthcare domain
while sharing common backend infrastructure with the other domains.

---

## API

The Healthcare domain exposes its functionality through the Know Nepal
REST API.

The frontend accesses healthcare information through the backend API
rather than directly accessing the database.

---

## Domain Boundary

The Healthcare domain owns healthcare-related information and data.

Other domains should interact with Healthcare through appropriate
application or API boundaries rather than directly accessing its
database.

---

## Related Documentation

- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
