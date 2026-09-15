# Existing System Analysis & Problem Statement

## Overview of the Current System
India's Digital India Land Records Modernization Programme (DILRMP) introduced the Unique Land Parcel Identification Number (ULPIN)—popularly known as an "Aadhaar for land"—as a 14-digit alphanumeric identifier assigned to every surveyed land parcel from its geo-referenced cadastral coordinates[span_1](start_span)[span_1](end_span). While ULPIN successfully establishes a single authoritative source of truth for ground footprints, it is inherently **two-dimensional**[span_2](start_span)[span_2](end_span).

## Limitations of Existing 2D Systems
As urban construction moves upward and underground, traditional 2D records fail to represent:
* **Multi-Storey Properties:** Stacked ownership units, high-rise apartments, and commercial complexes sharing a single ground footprint[span_3](start_span)[span_3](end_span).
* **Subsurface Infrastructure:** Basements, underground parking structures, and complex utility corridors (water, sewage, electricity, and telecom lines)[span_4](start_span)[span_4](end_span).
* **Vertical Boundaries:** Elevated or cantilevered structures and vertical boundaries separating adjoining units[span_5](start_span)[span_5](end_span).

## The Research Gap
While technologies like GIS, BIM, LiDAR, and standards like the Land Administration Domain Model (LADM / ISO 19152) are mature individually, a lightweight, India-specific integration that binds them directly to the operational ULPIN identifier was missing[span_6](start_span)[span_6](end_span). **ULPIN 3D** bridges this gap by adding a volumetric extension layer without replacing existing 2D land records[span_7](start_span)[span_7](end_span).
