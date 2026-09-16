# Project Diagrams

# 3D Building and Room Hierarchy

```mermaid
graph TD
    A[ULPIN ID] --> B[Building Model]
    B --> C1[Ground Floor]
    B --> C2[Upper Floors]
    C1 --> D1[Unit 101]
    C2 --> D2[Unit 201]
    D1 --> E1[Hall]
    D1 --> E2[Bedrooms]
    D1 --> E3[Kitchen]
    D2 --> F1[Master Bedroom]
    D2 --> F2[Balcony]
