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
| [SANOUKA](case-studies/sanouka.md) | Public transit & navigation app | Route planning, GTFS, OpenTripPlanner, Redis caching, Cloud Run optimization, offline maps, Firebase Auth. Route search improved from roughly 2 minutes to 6–10 seconds in common cases. |
| [Storix](case-studies/storix.md) | Warehouse and retail inventory system | Flutter product for stock movement, barcode workflows, local database, Supabase-backed operations, reporting, printing, and 100K+ inventory-record capacity. |
| [Import & Export System](case-studies/import-export-system.md) | Desktop operations system | Offline-first Flutter Desktop system with SQLite/FFI, Excel/PDF workflows, operational tables, role-based usage, and faster internal record handling. |
| [Nano City](case-studies/nano-city.md) | Marketplace mobile app | Product listing performance, REST API integration, Firebase, shopping-flow UI refinement, and Play Store delivery. |

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
- Firebase Auth, Firestore, Supabase, REST APIs, SQLite/Drift.
- Maps, geolocation, GTFS, OpenTripPlanner, OSRM, MBTiles.
- Offline-first product behavior and resilient fallbacks.
- Performance monitoring, caching, and production debugging.
- Business workflows: stock movement, reporting, printing, imports, exports, and role-based access.

---

If you want the short version: I build real Flutter products, not just screens.
