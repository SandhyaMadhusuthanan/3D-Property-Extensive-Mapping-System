# Project Diagrams

This folder contains the architecture diagrams, workflows and data-flow diagrams used in the ULPIN 3D project.

graph TD
    A[ULPIN Unique Land Parcel ID] --> B[Land Parcel / Plot]
    B --> C[Multi-Storey Building / Structure]
    C --> D[Floor / Level e.g., Ground, First]
    D --> E[Individual Apartment / Unit]
    E --> F[Room Breakdown: Hall, Bedroom, Kitchen, Balcony]

    flowchart LR
    A[GIS & Survey Data] --> B[ULPIN Database]
    C[Cadastral Maps] --> B
    B --> D[3D Property Mapping Engine]
    D --> E[Land Breakdown Views]
    D --> F[Room Breakdown Views]
    E --> G[Web/App User Interface]
    F --> G

    ```mermaid
graph TD
    A[ULPIN Unique Land Parcel ID] --> B[Land Parcel / Plot]
