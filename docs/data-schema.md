# Data Schema Documentation

This document outlines the data structure and hierarchy used in the **3D-Property-Extensive-Mapping-System** mockup to represent land parcels, multi-storey buildings, and room-level details.

## Overview of ULPIN Hierarchy

The system structures property data hierarchically from macro land plots down to micro room details:
1. **ULPIN (Unique Land Parcel Identification Number):** The root identifier for the land plot.
2. **Building Structure:** Multi-storey building or structure associated with the land parcel.
3. **Floor/Level:** Individual levels (e.g., Ground Floor, First Floor).
4. **Unit/Apartment:** Individual living spaces on a given floor.
5. **Room Breakdown:** Specific rooms (Hall, Bedrooms, Kitchen, Balcony, Bathrooms).

---

## Sample JSON Data Structure

In this client-side static mockup, property data is structured conceptually in JSON format to simulate how records are handled:

```json
{
  "ulpin": "IN-33-04-102-0012345",
  "propertyDetails": {
    "state": "Tamil Nadu",
    "district": "Coimbatore",
    "surveyNumber": "142/2A",
    "totalPlotAreaSqFt": 2400
  },
  "buildingStructure": {
    "buildingName": "Urban Heights",
    "totalFloors": 3,
    "selectedFloor": "First Floor",
    "unitNumber": "101"
  },
  "roomBreakdown": {
    "hallLiving": "240 sq ft",
    "masterBedroom": "180 sq ft",
    "secondBedroom": "150 sq ft",
    "kitchen": "110 sq ft",
    "balcony": "95 sq ft",
    "bathrooms": 2
  }
}
