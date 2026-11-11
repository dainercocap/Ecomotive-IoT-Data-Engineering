
# Data Quality – Ecomotive IoT

## Overview

Data quality controls are implemented across the Bronze, Silver, and Gold layers to ensure data reliability and consistency.

## Validation Rules

The Silver layer applies the following validation rules:

- Sensor ID must not be null or empty.
- Vehicle ID must not be null or empty.
- Temperature must be numeric and within the range of -40°C to 85°C.
- Latitude must be between -90 and 90.
- Longitude must be between -180 and 180.
- Battery level must be between 0% and 100%, when available.
- Sensor status values are standardized.

## Data Deduplication

Duplicate IoT events are identified using the sensor, vehicle, and reading timestamp as the event key.

Only one valid record per event is retained in Silver.

## Rejected Records

Records that fail validation rules are classified and stored in the rejected records table:

`ecomotive.silver.rechazos_iot_sensor`

## Gold Layer Controls

The Gold layer includes checks for:

- Dimension uniqueness.
- Referential integrity.
- Fact table event uniqueness.
- Silver-to-Gold reconciliation.

## Objective

Ensure data accuracy, consistency, traceability, and reliability throughout the IoT data pipeline.
