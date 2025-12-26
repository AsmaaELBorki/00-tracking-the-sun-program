# Data Contract — Tracking the Sun Analytical Program

This document defines the **shared analytical substrate** used across all
repositories in the Tracking the Sun program.

All downstream repositories assume compliance with this contract unless
explicitly stated otherwise.

---

## Source Dataset

**Name:** Tracking the Sun  
**Provider:** National Renewable Energy Laboratory (NREL)  
**Coverage:** United States  
**Temporal Range:** ~1998 – 2024  
**Unit of Observation:** Individual solar installation (system-level)

The dataset aggregates installation-level records across jurisdictions,
installers, and customer segments.

---

## Canonical Record Definition

Each row represents a **single photovoltaic system installation** and includes:
- system size (DC capacity)
- installation date
- customer and ownership attributes
- geographic identifiers
- equipment configuration fields (e.g., inverter quantities)
- installer identifiers

Multiple records do **not** represent time series per system.

---

## Required Core Fields

All downstream repositories assume the presence and semantic correctness of:

- `pv_system_size_dc`
- `installation_date`
- `customer_segment`
- `installer_name_standardized`
- `county`
- `inverter_quantity_1`

Additional inverter quantity fields may exist and are handled explicitly
where relevant.

---

## Validity Assumptions

After validation (Repo 0 / Repo 1):

- `pv_system_size_dc > 0`
- inverter quantities are non-negative
- installation dates are coercible to datetime
- sentinel values (e.g., -1) are normalized to `NaN`
- schema is stable across repos

No downstream repo re-cleans raw data unless stated.

---

## Observational Nature

This dataset is **observational**:
- no counterfactuals
- no randomized assignment
- no direct demand measurements

All analyses are descriptive, comparative, or predictive — **not causal**.

---

## Temporal Semantics

- `installation_date` reflects commissioning date
- time is treated as:
  - a conditioning variable (Repo 1 & 2)
  - an evolutionary signal (Repo 3)
  - a predictive feature (Repo 4)

No repo treats time as a causal intervention.

---

## Modification Policy

Downstream repositories:
- may derive new features
- may filter records conditionally
- may aggregate or cohort data

They may **not** redefine raw field semantics.

Any deviation must be documented locally.

---

## Contract Stability

This contract is expected to be stable across the program lifecycle.
Breaking changes require:
- explicit versioning
- documentation
- downstream impact assessment

