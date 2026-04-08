# PostGIS spatial database workflows

## Overview

This repository demonstrates working with spatial data in a PostgreSQL database using PostGIS within a containerized development environment. The project focuses on writing SQL queries to analyze vector spatial data, perform geometry operations, evaluate spatial relationships, and execute spatial joins.

## Workflow

This project follows a structured spatial database workflow:

1. Set up a PostGIS database using Docker in GitHub Codespaces  
2. Load spatial datasets into the database using `shp2pgsql`  
3. Connect to the database using the VS Code PostgreSQL extension  
4. Write and execute SQL queries across multiple exercise files  
5. Perform spatial analysis directly within the database  
6. Track and manage changes using Git version control  

This workflow highlights the shift from desktop or notebook-based analysis to database-driven geospatial processing.

## SQL exercises

The assignment is organized into four SQL files, each focusing on a different aspect of spatial analysis:

### 1. Basic SQL queries
- Aggregating population data (e.g., total Asian population, Manhattan population)
- Calculating percentages and averages by borough
- Using grouping and aggregation functions

### 2. Geometry queries
- Calculating area and length using spatial functions (`ST_Area`, `ST_Length`)
- Converting units (meters to acres, miles)
- Working with geometry structure (e.g., multipart geometries, interior rings)
- Exporting geometries to GeoJSON

Example: Calculated total area of the Bronx using `ST_Union` and unit conversion.

### 3. Spatial relationships
- Identifying intersections between features (`ST_Intersects`)
- Performing proximity analysis (`ST_DWithin`)
- Using subqueries to reference geometries dynamically

Example: Determined neighborhoods intersecting Queensboro Bridge and nearby population within 50 meters.

### 4. Spatial joins
- Joining datasets using spatial relationships
- Querying transit accessibility and neighborhood coverage
- Calculating population totals and densities

Example: Computed population density for East and West Village using spatial joins and area calculations.

## Repository structure

    .
    ├── README.md
    ├── .devcontainer
    │   ├── devcontainer.json
    │   └── Dockerfile
    ├── sql/
    │   ├── 01_basic_sql_queries.sql
    │   ├── 02_geometry_queries.sql
    │   ├── 03_spatial_relationships.sql
    │   └── 04_spatial_joins.sql
    ├── demos/
    │   ├── demo_aggregation_queries.sql
    │   ├── demo_basic_queries.sql
    │   ├── demo_filtering_queries.sql
    │   └── demo_postgis_queries.sql
    └── docker-compose.yml


- `sql/` — completed assignment queries and exercises  
- `demos/` — example queries from lectures  
- `.devcontainer/` — Codespaces development environment configuration  
- `docker-compose.yml` — configuration for running the PostGIS database container  

## Notes

- SQL queries are written and executed directly within the `sql/` files using the PostgreSQL extension in VS Code  
- Spatial data is downloaded and loaded into the database within the Codespaces environment and is not stored in this repository  
- The database runs in a separate Docker container configured with PostGIS  
- Queries rely on a projected CRS (UTM Zone 18N, EPSG:26918), ensuring that distance and area calculations return values in meters 
