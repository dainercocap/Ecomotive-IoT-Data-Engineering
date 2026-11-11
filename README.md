## Development Workflow

This project uses Git branching and version control to manage development changes.
# Ecomotive IoT – Data Engineering

## Project Overview

End-to-end Data Engineering project focused on processing IoT sensor data from connected vehicles using Databricks.

The project simulates an IoT monitoring environment where sensor readings such as temperature, battery levels, GPS coordinates, and device status are ingested, validated, transformed, and integrated for analytical purposes.

## Architecture

The solution follows the **Medallion Architecture**:

- **Bronze:** Raw data ingestion using Databricks Auto Loader.
- **Silver:** Data cleansing, validation, standardization, and deduplication.
- **Gold:** Dimensional modeling using a Star Schema.

## Technology Stack

- Databricks
- Apache Spark
- PySpark
- SQL
- Delta Lake
- Unity Catalog
- Auto Loader
- Databricks Workflows

## Data Model

The Gold layer implements a **Star Schema** composed of:

- `fact_lecturas_iot`
- `dim_sensores`
- `dim_vehiculos`
- `dim_fecha`

## Data Quality

Validation rules, rejected records management, event deduplication, referential integrity, and data reconciliation controls.

## Orchestration

End-to-end pipeline orchestration using Databricks Workflows, coordinating ingestion, transformation, dimensional integration, data quality checks, and analytical views.

## Repository Structure

```text
SRC/
├── DDL/
├── ETL/
├── TESTING/
└── VIEWS/
```

## Project Status

End-to-end pipeline implemented and tested in Databricks Free Edition.
