# Existing System Analysis & Problem Statement

## Overview of the Current System
India's Digital India Land Records Modernization Programme (DILRMP) introduced the Unique Land Parcel Identification Number (ULPIN)—popularly known as an "Aadhaar for land"—as a 14-digit alphanumeric identifier assigned to every surveyed land parcel from its geo-referenced cadastral coordinates. While ULPIN successfully establishes a single authoritative source of truth for ground footprints, it is inherently two-dimensional.

## Limitations of Existing 2D Systems
As urban construction moves upward and underground, traditional 2D records fail to represent:
* **Multi-Storey Properties:** Stacked ownership units, high-rise apartments, and commercial complexes sharing a single ground footprint.
* **Subsurface Infrastructure:** Basements, underground parking structures, and complex utility corridors (water, sewage, electricity, and telecom lines).
* **Vertical Boundaries:** Elevated or cantilevered structures and vertical boundaries separating adjoining units.

## The Research Gap
While technologies like GIS, BIM, LiDAR, and standards like the Land Administration Domain Model (LADM / ISO 19152) are mature individually, a lightweight, India-specific integration that binds them directly to the operational ULPIN identifier was missing. ULPIN 3D bridges this gap by adding a volumetric extension layer without replacing existing 2D land records.
