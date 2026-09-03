# Wildlife

## Overview

The **Wildlife** domain provides structured information about Nepal's
wildlife and natural environment.

It allows users to explore national parks, wildlife species, flora, and
lakes across Nepal.

---

## Domain Scope

The Wildlife domain covers:

- National parks
- Wildlife species
- Flora
- Lakes

---

## Data

Wildlife data is stored within the Wildlife domain's PostgreSQL
database.

The domain maintains its own persistence boundary within the Know Nepal
backend.

---

## Backend

The Wildlife domain is implemented as a module within the Spring Boot
modular monolith.

Its application responsibilities remain within the Wildlife domain
while sharing common backend infrastructure with the other domains.

---

## API

The Wildlife domain exposes its functionality through the Know Nepal
REST API.

The frontend accesses wildlife information through the backend API
rather than directly accessing the database.

---

## Domain Boundary

The Wildlife domain owns wildlife and natural-environment data.

Other domains should interact with Wildlife through appropriate
application or API boundaries rather than directly accessing its
database.

---

## Related Documentation

- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
