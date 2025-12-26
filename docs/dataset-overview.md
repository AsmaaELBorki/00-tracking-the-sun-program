# Dataset Overview — Tracking the Sun (California)

## Dataset Origin

**Tracking the Sun** is a long-running longitudinal dataset published by the  **National Renewable Energy Laboratory (NREL)**.

It aggregates photovoltaic (PV) installation-level data reported by state agencies, utilities, incentive programs, and interconnection records across the United States.

The dataset is widely cited in:
- academic research
- policy analysis
- industry reports
- grid planning studies

---

## Temporal Coverage

The dataset spans approximately:

**1998 → 2024**

Coverage varies by jurisdiction and reporting program.
Earlier years reflect sparse adoption; later years reflect market maturation.

This long time horizon enables:
- technology evolution analysis
- scaling regime identification
- policy-era comparisons

---

## Geographic Scope

The full Tracking the Sun dataset is national.

This analytical program **restricts scope to California**, which is justified because California:

- has the longest continuous reporting history
- represents the largest residential solar market in the U.S.
- spans multiple regulatory, climatic, and utility regimes
- exhibits early adoption, saturation, and consolidation phases

California is treated as a **self-contained solar economy** rather than a sample of the national market.

---

## Unit of Observation

Each row represents a **single solar installation** (system-level).

The dataset is **not**:
- a time series per household
- a panel per customer
- a per-inverter dataset

Multiple rows do not track the same system over time.

---

## Core Variables (Conceptual)

The dataset captures four conceptual domains:

1. **System Characteristics**
   - DC system size
   - equipment quantities
   - technology flags

2. **Configuration Architecture**
   - inverter counts
   - multi-phase indicators
   - expansion flags

3. **Contextual Attributes**
   - customer segment
   - ownership model
   - new construction vs retrofit

4. **Spatiotemporal Context**
   - installation date
   - county
   - utility service territory

---

## Analytical Value

The dataset is uniquely suited to study:

- how systems are sized
- how configuration choices scale with size
- how norms evolve over time
- where deviations cluster
- how policy and market maturation affect architecture

It supports **descriptive**, **comparative**, and **predictive** analysis, but not causal inference without external augmentation.

---

## Known Limitations

- No direct measurement of household demand
- No inverter efficiency curves
- No customer income data
- Reporting completeness varies by year

All conclusions must be framed as **observed behavior**, not optimality.

---

## Why This Dataset

Tracking the Sun is valuable precisely because it captures:
- real-world decisions
- at massive scale
- across two decades
- under evolving constraints

This program treats the dataset as an empirical record of **how solar systems were actually built**, not how they should have been built.
