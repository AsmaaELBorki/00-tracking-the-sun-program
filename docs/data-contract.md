# Data Contract

This document defines the analytical contract shared across all
repositories in the Tracking the Sun program.

## Canonical Dataset

The canonical validated dataset is produced once and only once.

- File: `tracking_the_sun_CA_2024_cleaned.parquet`
- Producer: Program-level validation pipeline
- Status: trusted analytical substrate

Downstream repositories:
- MUST NOT load raw data
- MUST NOT re-clean base fields
- MAY derive new features from the canonical dataset

## Guarantees

The canonical dataset guarantees:
- physically plausible system sizes
- valid inverter counts
- normalized sentinel values (e.g. -1 → NaN)
- standardized categorical fields where applicable
- consistent date parsing

## Non-Guarantees

The dataset does NOT guarantee:
- causal validity
- completeness across all years
- absence of reporting bias
- suitability for regulatory enforcement

All analyses must operate within these constraints.
