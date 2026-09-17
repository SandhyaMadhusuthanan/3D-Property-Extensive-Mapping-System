# Proposed Solution

## Core Idea: Sub-Parcel ULPINs

Instead of one ULPIN per plot, this system proposes that **every vertical layer of a property gets its own sub-parcel ULPIN**, derived from and linked to the parent land ULPIN. This includes:

- Individual floors of a building
- Individual apartment units / shops / offices within a floor
- Individual parking bays (allotted, visitor, EV charging, unallotted)
- Common areas (entrance, terrace, basement)
- Air rights above the roof (unbuilt but claimable vertical space)

Each sub-parcel is independently searchable, but always traceable back to the single base ULPIN of the land it sits on — preserving a clean parent-child relationship instead of fragmenting the record.

## Role-Based Views

The prototype implements two login roles with different vantage points on the same data:

- **Government Official** — sees a city-wide dashboard: total tracked area, plots, buildings, and portfolio value, with the ability to drill into any layout, building, or plot.
- **Property Owner / Citizen** — logs in against their own Aadhaar-linked profile and sees only what's registered to them, plus tools to locate and navigate to their own plot.

## Key Solution Components

1. **Interactive Overview Map** — A city-zone map (map/satellite toggle) showing all lands, apartments, shops, and complexes, filterable by category, with an elevated-transit-corridor overlay to show how infrastructure projects intersect with tracked land.

2. **Joint Ownership Module** — A dedicated view for group-purchased land parcels, showing the shared ULPIN, each member's percentage share, a full ownership history (registrations and share transfers), and a separate record of former owners who have fully exited (Aadhaar unlinked, contact retained for record purposes only).

3. **3D Building & Floor Breakdown** — Every building can be opened into a floor-by-floor 3D breakdown, and every floor into individual titled units, vacant units, and common areas — each clickable to reveal its own sub-parcel ULPIN.

4. **Parking as a First-Class Record** — Every parking bay is modeled as its own sub-parcel, tagged as allotted-to-a-unit, visitor, EV-charging, or unallotted, closing the "whose parking spot is this" gap.

5. **Land Value & Government Amenity Impact** — For any plot, the system shows how nearby government amenities and announced infrastructure projects add measurable premiums over the base guideline value, plus a 10-year year-by-year projected value chart with project milestones priced in.

6. **Find My Plot** — A navigation tool for buyers standing at a large layout with many look-alike plots: it highlights their specific plot on the map and gives walking distance/time and outdoor directions to the site.

7. **3D / 360° Building Model Viewer** — A rotatable, zoomable exterior 3D concept model of a building (front/rear/left/right/roof), so a buyer or official can visually understand the structure before checking floor-level ownership data.

## What Makes This Different from Existing ULPIN

| Existing ULPIN (2D) | This Proposed Extension (3D) |
|---|---|
| One ID per land parcel | One ID per parcel **and** one per vertical sub-unit |
| No floor/unit-level ownership | Floor, unit, and parking-level ownership |
| No joint-ownership share tracking | Full share % and transfer history per member |
| Flat map only | Interactive 3D model + map + amenity/value data |
| No buyer navigation tool | "Find My Plot" GPS-guided navigation |

## Important Caveat

This is a **conceptual, prototype-level solution** built on mock data for demonstration. Real deployment would require integration with actual government land databases, a surveyed (not illustrative) 3D geometry pipeline, and legal/policy work to formally recognize sub-parcel ULPINs — all discussed further in `Future-Scope.md`.
