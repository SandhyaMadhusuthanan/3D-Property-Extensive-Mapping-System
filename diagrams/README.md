# Project Diagrams

This folder contains the architecture diagrams, workflows and data-flow diagrams used in the ULPIN 3D project.

graph TD
    A[User / Client UI] -->|Login / ULPIN Search| B[Frontend Application]
    B -->|API Requests| C[Backend Server Services]
    C -->|Query Records| D[(ULPIN & Land Records Database)]
    C -->|Spatial Processing| E[3D Property Mapping Engine]
    E -->|Rendered View & Layouts| B

    sequenceDiagram
    actor User
    participant UI as Web/App UI
    participant API as Backend API
    participant DB as ULPIN Database
    participant Engine as 3D Visualizer

    User->>UI: Enter ULPIN / Credentials
    UI->>API: Request Property & Land Data
    API->>DB: Query Spatial & Ownership Records
    DB-->>API: Return Property Metadata
    API-->>UI: Send JSON Data (Land/Room Breakdown)
    UI->>Engine: Initialize 3D Model View
    Engine-->>User: Display Interactive 3D Property Map
