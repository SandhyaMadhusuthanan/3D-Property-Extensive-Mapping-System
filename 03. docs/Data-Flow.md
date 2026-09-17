# Data Flow

## Prototype Data Flow (Current, Client-Only)

Since the current prototype has no backend, "data flow" describes how data moves *within the browser*, from hardcoded JavaScript objects to rendered screens.

```
[Login Form Input]
        │
        ▼
[JS: validate against hardcoded demo credentials]
        │
        ▼
[Set role: Government Official | Owner/Citizen]
        │
        ▼
[Render App Shell + role-specific Dashboard]
        │
        ▼
[User clicks: Overview Map / Property Category / Find My Plot]
        │
        ▼
[JS: filter in-memory mock dataset by category/status]
        │
        ▼
[Render: Map pins → Layout → Plot → Building → Floor → Unit → Parking Bay]
        │
        ▼
[User clicks a sub-parcel (e.g., a unit or parking bay)]
        │
        ▼
[JS: look up that sub-parcel's mock record]
        │
        ▼
[Render: sub-parcel ULPIN, ownership/tenant info, household or shop details]
```

Every "drill-down" (city → layout → plot → building → floor → unit → parking bay) is simply a deeper lookup into the same nested mock-data structure — there's no network round trip.

## Proposed Production Data Flow

```
1. User Action (e.g., "open Plot #142")
        │
        ▼
2. Frontend sends authenticated API request
   (JWT / Aadhaar-verified session token)
        │
        ▼
3. Backend API Gateway
   - Validates token & role permissions
        │
        ▼
4. ULPIN Service
   - Resolves base ULPIN → fetches sub-parcel tree
   - Fetches ownership/share-transfer ledger entries
        │
        ▼
5. Valuation Service (if plot/value view requested)
   - Pulls guideline value + amenity premiums
   - Computes 10-year projection with project milestones
        │
        ▼
6. GIS Service (if map/navigation view requested)
   - Returns geo-coordinates, boundaries, routing data
        │
        ▼
7. Backend aggregates responses → returns JSON to frontend
        │
        ▼
8. Frontend renders map pins, 3D model, ownership cards, or value charts
```

## Ownership Change Flow (e.g., Share Transfer in Joint Ownership)

```
[Registered event: Member A transfers 15% share to Member C]
        │
        ▼
[Backend appends new entry to Ownership History ledger — never overwrites]
        │
        ▼
[Member A's remaining share recalculated]
        │
        ▼
[If Member A's share reaches 0%]
        │
        ▼
[Member A moved to "Former Owners" list, Aadhaar unlinked from ULPIN]
        │
        ▼
[Member C added to active "Members Linked to this ULPIN" list]
```

This append-only ledger design ensures the full ownership history remains auditable — nothing is deleted, only superseded by newer, timestamped events.

## Key Data Entities

| Entity | Key Fields | Linked To |
|---|---|---|
| Base ULPIN | 14-digit ID, location, total extent | Sub-parcels |
| Sub-Parcel ULPIN | Type (floor/unit/parking/air-rights), status | Base ULPIN |
| Owner/Tenant Record | Aadhaar ID, share %, role (owner/tenant) | Sub-parcel |
| Ownership History Event | Type (registration/transfer), date, parties | Base/Sub ULPIN |
| Valuation Record | Guideline value, amenity premiums, year | Base ULPIN |
