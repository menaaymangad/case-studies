# SANOUKA — Public Transit & Navigation Case Study

![SANOUKA preview](https://minaayman-portfolio.netlify.app/images/sanouka.png)

SANOUKA is a public transit and navigation app for Abidjan, Côte d'Ivoire. It helps commuters search for routes, understand available transport options, view stops, and navigate through the city using public transport, walking segments, and offline map support.

I owned the project end-to-end as a solo Flutter/Product Engineer: app architecture, Flutter implementation, map experience, route search, authentication, GTFS integration, API integration, performance tuning, release work, and ongoing technical decisions.

[Portfolio case](https://minaayman-portfolio.netlify.app/#/en/work) · [App Store](https://apps.apple.com/sa/app/sanouka/id6756220634?l=ar) · [Play Store](https://play.google.com/store/apps/details?id=com.sanouka.app)

---

## Summary

| Area | Details |
| --- | --- |
| Product | Public transit and city navigation app |
| Market | Abidjan, Côte d'Ivoire |
| Role | Solo Flutter Product Engineer |
| Platforms | Android, iOS work, Flutter app architecture |
| Core stack | Flutter, Dart, Firebase Auth, OpenStreetMap, GTFS, OpenTripPlanner, Cloud Run, Redis, MBTiles |
| Main challenge | Make complex transit routing fast, reliable, and usable on mobile |
| Key result | Route planning improved from roughly 2 minutes to 6–10 seconds in common cases |

---

## The problem

Public transport information in many cities is fragmented. A user may need to understand routes, nearby stops, walking segments, vehicle types, and route timing while dealing with unstable connectivity or slow network conditions.

For SANOUKA, the technical challenge was not only showing a map. The product needed to combine several difficult pieces:

- official transit data through GTFS;
- route calculation through OpenTripPlanner;
- mobile map rendering and location services;
- geocoding and reverse-geocoding;
- offline map access;
- authentication and user sessions;
- performance good enough for everyday commuting.

---

## My role

I handled the project as an end-to-end owner, not as a narrow feature contributor.

My responsibilities included:

- designing the Flutter app structure;
- building feature modules with Clean Architecture;
- implementing route search and map flows;
- integrating OpenTripPlanner route planning;
- working with GTFS data and local transit files;
- adding Firebase authentication flows;
- improving route-search performance;
- adding offline map support using MBTiles;
- tuning API, caching, and infrastructure behavior;
- preparing production-ready builds and store-facing delivery work.

---

## Product and data scale

The app worked with a real transit dataset rather than small mock data.

Known data coverage included:

- **635** public transit routes;
- **7,251** transit stops;
- **29** transport agencies;
- **1,304** scheduled trips per day;
- local GTFS files bundled for offline access;
- Abidjan boundary/geofencing data;
- offline raster map tiles through MBTiles.

This pushed the app beyond a normal CRUD-style mobile project. Data loading, caching, parsing, routing, and UI responsiveness all mattered.

---

## Architecture

SANOUKA used a feature-based Clean Architecture structure.

```mermaid
flowchart TD
  UI[Flutter UI] --> State[Bloc / Cubit state]
  State --> UseCase[Route search use cases]
  UseCase --> Repository[Repository layer]
  Repository --> Remote[OTP / API data source]
  Repository --> Local[Local GTFS and offline assets]
  Remote --> Cache[Redis cache]
  Cache --> OTP[OpenTripPlanner]
  Local --> GTFS[GTFS files]
  UI --> Maps[OpenStreetMap / MBTiles]
  UI --> Auth[Firebase Auth]
```

The main reason for this structure was maintainability. Route search, maps, auth, onboarding, and offline services could evolve without turning the whole app into one large coupled module.

---

## Route planning challenge

The hardest product flow was route planning.

The app needed to send origin/destination coordinates to an OpenTripPlanner backend, process GTFS-backed route results, show transit legs, walking legs, intermediate stops, route names, polylines, and readable instructions.

Early route searches could take around **120 seconds** in some cases. That was not acceptable for a commuter experience.

I improved this by combining several changes:

- using Redis caching for repeated and similar route requests;
- reducing repeated OpenTripPlanner calculations;
- tuning Cloud Run resource choices around cost and speed;
- keeping a warm Cloud Run instance for critical route flows;
- improving request handling and route parsing;
- using fallbacks so users still get useful behavior when a service fails.

The result: common route-search scenarios dropped from roughly **2 minutes** to **6–10 seconds**.

That is approximately a **12x–20x improvement** in perceived route-search speed.

---

## Performance and cost tradeoff

One important decision was balancing infrastructure cost with user experience.

OpenTripPlanner can be resource-heavy. Keeping everything oversized would improve raw speed but increase client cost. Scaling everything down too aggressively would save money but hurt route-search latency and cold starts.

The final direction was a pragmatic middle ground:

- reduce unnecessary Cloud Run resource usage where possible;
- use Redis to avoid recalculating repeated route plans;
- keep minimum instances warm for critical routing availability;
- use caching and request deduplication to reduce backend pressure.

This is the kind of tradeoff I care about in production work: not just making something work, but making it usable, maintainable, and cost-aware.

---

## What to ask me about this project

If this comes up in an interview, useful discussion areas are:

- how GTFS and OpenTripPlanner fit together;
- why Redis helped route-search latency;
- how I approached Cloud Run speed/cost tradeoffs;
- how offline MBTiles changed the user experience;
- what I would measure more carefully if I restarted the project today.

---

## Privacy note

This case study intentionally avoids exposing private repository code, credentials, deployment secrets, or sensitive infrastructure details. It focuses on the public-safe product story and engineering decisions.
