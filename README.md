# Project Log: Reentry Resource Allocation & Service Desert Analysis

## 1. Project Objective
**Strategic Goal:** To optimize the placement of community corrections resources by identifying "Service Deserts"—geographic areas with high densities of returning citizens (parolees) but low access to state-funded support infrastructure (e.g., substance abuse clinics, workforce development).

**Technical Goal:** To demonstrate **Geospatial Intelligence (GIS)** capabilities using Python (`GeoPandas`) and Power BI to perform spatial joins, distance calculations, and heatmap visualization for policy decision-making.

## 2. Architecture & Workflow
This project utilizes a modular directory structure to handle heavy geospatial files (`.shp`) separately from code logic.

* **`01_data_cleaning/`**: Scripts to ingest and standardize Open Data (facility locations) and generate synthetic parolee addresses.
* **`02_geospatial_analysis/`**: Python logic for Coordinate Reference System (CRS) transformations and proximity analysis (calculating "Distance to Nearest Resource").
* **`03_visualization/`**: Power BI assets for map layers and density heatmaps.
* **`04_shapefiles/`**: Local storage for Michigan County boundaries and road networks (Ignored by Git to prevent bloat).

## 3. Data Strategy (Hybrid Approach)
To balance real-world relevance with privacy compliance, this project uses a hybrid data model:

* **Infrastructure (Real Data):** Publicly available shapefiles from the [State of Michigan GIS Open Data Portal](https://gis-michigan.opendata.arcgis.com/) representing real Probation Offices and Community Service providers.
* **Offender Locations (Synthetic):** To protect PII, I will engineer a **Spatial Generation Script** that creates random lat/long coordinates constrained within specific high-density census tracts, mimicking realistic population clusters without exposing actual home addresses.