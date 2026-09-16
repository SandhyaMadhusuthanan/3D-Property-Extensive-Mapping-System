# Project Diagrams

```mermaid
graph TD
    A[ULPIN ID] --> B[Land Parcel]
    B --> C[Building Structure]
    C --> D[Floor / Unit]
    D --> E[Room Breakdown]

```mermaid
graph TD
    A[ULPIN Land Parcel ID] --> B[Multi-Storey 3D Building Model]
    
    B --> C1[Ground Floor / Level 01]
    B --> C2[Upper Floors / Levels 02+]
    
    C1 --> D1[Apartment / Unit 101]
    C2 --> D2[Apartment / Unit 201]
    
    D1 --> E1[Hall / Living Area]
    D1 --> E2[Bedrooms 1 & 2]
    D1 --> E3[Kitchen]
    D1 --> E4[Bathrooms & Utility]
    
    D2 --> F1[Master Bedroom Suite]
    D2 --> F2[Secondary Bedroom]
    D2 --> F3[Balcony & Passage]
