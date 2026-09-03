# Destinations

## Overview

The **Destinations** domain provides structured information for
discovering and planning travel across Nepal.

It allows users to explore destinations, trekking routes, itineraries,
and related travel information.

The domain also supports the Know Nepal AI trip-planning experience.

---

## Domain Scope

The Destinations domain covers:

- Tourist destinations
- Trekking routes
- Curated itineraries
- Destination categories
- Destination media
- Travel-related information
- AI-assisted trip planning

---

## Trip Planning

The domain provides an AI-assisted trip-planning experience that uses
Know Nepal destinations and itineraries to create personalized
day-by-day travel plans.

Users can provide information such as destination or region, trip
duration, pace, budget, interests, and additional notes.

---

## Data

Destination and itinerary data is stored within the Destinations
domain's PostgreSQL database.

The domain maintains its own persistence boundary within the Know Nepal
backend.

---

## Backend

The Destinations domain is implemented as a module within the Spring
Boot modular monolith.

Its application responsibilities remain within the Destinations domain
while sharing common backend infrastructure with the other domains.

---

## API

The Destinations domain exposes its functionality through the Know
Nepal REST API.

The frontend accesses destination and itinerary information through
the backend API rather than directly accessing the database.

---

## Domain Boundary

The Destinations domain owns destination, route, and itinerary-related
data.

Other domains should interact with Destinations through appropriate
application or API boundaries rather than directly accessing its
database.

---

## Related Documentation

- [Backend Architecture](../architecture/backend.md)
- [Data Architecture](../architecture/data.md)
