# Mina Ayman Gad — Product Engineering Case Studies

Selected case studies from production Flutter projects I have owned end-to-end.

This repository is a public, safe companion to my portfolio. It focuses on product decisions, engineering tradeoffs, architecture, and measurable outcomes — without exposing private client code, secrets, credentials, or production internals.

[Portfolio](https://minaayman-portfolio.netlify.app) · [LinkedIn](https://www.linkedin.com/in/mina-ayman-gad/) · [GitHub](https://github.com/menaaymangad) · [Email](mailto:menaaymangad@gmail.com)

---

## About my work

I build Flutter products across mobile, web, and desktop, usually owning the full lifecycle:

- product scoping and technical planning;
- Flutter architecture and implementation;
- API, Firebase, Supabase, SQLite, and offline-first integrations;
- performance optimization and debugging;
- release preparation and store delivery;
- long-term maintenance and iteration.

My strongest work sits around practical products: maps, transport routing, offline data, inventory systems, business workflows, and cross-platform internal tools.

---

## Case studies

| Case study | Product type | Highlights |
| --- | --- | --- |
| [SANOUKA](case-studies/sanouka.md) | Public transit & navigation app | Route planning, GTFS, OpenTripPlanner, Redis caching, Cloud Run optimization, offline maps, Firebase Auth. Route search improved from roughly 2 minutes to under 10 seconds in common cases. |
| Storix | Warehouse management system | Cross-platform inventory workflows, stock movement tracking, scalable architecture for 100K+ records. Coming next. |
| Import & Export System | Desktop management system | Offline-first desktop operations, SQLite optimization, role-based workflows. Coming next. |
| Nano City | Marketplace mobile app | REST API integration, product listing performance, shopping-flow UI improvements. Coming next. |

---

## Why the source code is not public

Most projects here are production or client-facing systems. Their repositories may contain private business logic, protected workflows, or deployment-specific configuration.

Instead of exposing private source code, these case studies show the parts that matter for evaluation:

- what problem the product solved;
- what I personally owned;
- what technical choices I made;
- what tradeoffs I handled;
- what measurable result came out of the work.

---

## Engineering themes

- Flutter mobile, web, and desktop delivery.
- Clean Architecture, Bloc/Cubit, Riverpod, Provider, GetIt.
- Firebase Auth, Firestore, Supabase, REST APIs, SQLite.
- Maps, geolocation, GTFS, OpenTripPlanner, OSRM, MBTiles.
- Offline-first product behavior and resilient fallbacks.
- Performance monitoring, caching, and production debugging.

---

If you want the short version: I build real Flutter products, not just screens.
