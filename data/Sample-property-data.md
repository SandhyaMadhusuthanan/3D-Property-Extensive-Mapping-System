# Sample Property Dataset

This document provides a sample mock property record used by the client-side **3D-Property-Extensive-Mapping-System** to demonstrate ULPIN tracking, land breakdowns, and multi-storey room mapping.

## Property Record Example

```json
{
  "ulpin": "IN-33-04-102-0012345",
  "metadata": {
    "state": "Tamil Nadu",
    "district": "Coimbatore",
    "taluk": "Coimbatore North",
    "surveyNumber": "142/2A"
  },
  "landBreakdown": {
    "totalPlotAreaSqFt": 2400,
    "builtUpAreaSqFt": 1500,
    "openPlotAreaSqFt": 900
  },
  "buildingStructure": {
    "buildingName": "Urban Heights",
    "totalFloors": 3,
    "floors": [
      {
        "level": "Ground Floor",
        "units": ["Parking Area", "Common Lobby"]
      },
      {
        "level": "First Floor",
        "unitNumber": "101",
        "roomBreakdown": {
          "hallLiving": "240 sq ft",
          "masterBedroom": "180 sq ft",
          "secondBedroom": "150 sq ft",
          "kitchen": "110 sq ft",
          "balcony": "95 sq ft",
          "bathrooms": "2 units"
        }
      }
    ]
  }
}
