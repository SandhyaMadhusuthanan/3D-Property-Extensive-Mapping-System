# System Architecture

## Prototype Architecture (Current)

The current prototype is a **single-tier, client-only architecture**:

```
┌─────────────────────────────────────────────┐
│              Browser (Client)                │
│                                               │
│   index.html                                 │
│   ├── HTML structure (all screens)           │
│   ├── CSS (embedded design system)           │
│   └── JavaScript                             │
│        ├── Auth simulation (role-based)      │
│        ├── Mock data (Salem city dataset)    │
│        ├── View/router logic                 │
│        ├── Map filter logic                  │
│        └── 3D model interaction logic        │
└─────────────────────────────────────────────┘
```

There is no server, no database, and no network call — every screen is rendered from in-memory JavaScript data.

## Screen / Module Map

```
Login Screen
 └── Role selection: Government Official | Owner/Citizen
      └── App Shell
           ├── Dashboard (Govt)  — city stats: area, plots, buildings, portfolio value
           ├── Overview Map      — map/satellite toggle, category filters
           │    ├── Lands → Land Layouts → Joint Ownership Plots
           │    ├── Apartments → Building → Floors → Units → Parking/Residents
           │    ├── Shops → Shop details → Parking bays
           │    └── Complexes
           ├── My Properties (Owner) — Aadhaar-linked personal records
           └── Find My Plot (Tool)   — locate + navigate to owned plot
```

## Proposed Production Architecture (Future)

```
┌───────────────┐     ┌──────────────────┐     ┌────────────────────┐
│   Frontend    │────▶│   Backend API     │────▶│     Database        │
│ (React + Map  │     │ (REST/GraphQL)    │     │ (PostgreSQL+PostGIS)│
│  + 3D viewer) │◀────│                   │◀────│  ULPIN hierarchy,    │
└───────────────┘     │  - Auth service   │     │  ownership ledger,   │
        │              │  - ULPIN service  │     │  sub-parcel records  │
        │              │  - Valuation svc  │     └────────────────────┘
        ▼              └──────────────────┘
┌───────────────┐              │
│  Aadhaar /    │              ▼
│  Govt ID      │      ┌──────────────────┐
│  Verification │      │  GIS / Mapping    │
└───────────────┘      │  Service          │
                        └──────────────────┘
```

### Layer Responsibilities

- **Frontend** — renders dashboards, maps, 3D models, and forms; calls backend APIs; has no direct database access.
- **Backend API** — validates requests, enforces role-based access (Government Official vs Citizen), and orchestrates calls to the ULPIN service, valuation service, and GIS layer.
- **ULPIN Service** — owns the parent-child hierarchy: base ULPIN → sub-parcel ULPINs (floor, unit, parking bay, air rights), and the ownership/share-transfer ledger.
- **Valuation Service** — computes guideline-value + amenity-premium + project-milestone projections for the 10-year land value chart.
- **GIS/Mapping Service** — supplies real geo-coordinates, plot boundaries, and routing for the "Find My Plot" navigation feature.
- **Database** — stores all persistent records; PostGIS extension recommended for spatial queries (plot boundaries, distance calculations).
- **Identity Verification** — integrates with Aadhaar or an equivalent government ID system for authenticated, non-simulated logins.

## Data Ownership Hierarchy (Conceptual Model)

```
Base ULPIN (Land Parcel)
 ├── Sub-Parcel: Floor 1
 │    ├── Sub-Parcel: Unit 101 (owner/tenant record)
 │    ├── Sub-Parcel: Unit 102
 │    └── Sub-Parcel: Common Area
 ├── Sub-Parcel: Floor 2 ...
 ├── Sub-Parcel: Basement Parking
 │    ├── Bay 1 (allotted → Unit 101)
 │    ├── Bay 2 (visitor)
 │    └── Bay 3 (EV charging)
 └── Sub-Parcel: Air Rights (unbuilt)
```

This hierarchy is the architectural core of the entire system — every feature (ownership, parking, valuation, joint ownership) is built as a query against this tree.
