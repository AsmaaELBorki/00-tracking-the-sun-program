# Repository Dependencies — Tracking the Sun Program

This document explains how repositories relate to one another.

Repositories are **not nested** and **do not import code from each other**.
Dependencies are logical, not programmatic.

---

## Dependency Graph (Conceptual)

Repo 1 → Repo 2 → Repo 3 → Repo 4

All repos depend on the shared data contract.

---

## Repo 1 — System Size Determinants
**Inputs:** validated substrate  
**Outputs:** system size context features  
**Depends on:** data contract only  

---

## Repo 2 — System Configuration & Inverter Architecture
**Inputs:** validated substrate  
**Uses:** outputs from Repo 1 conceptually  
**Outputs:** configuration-level features  

---

## Repo 3 — Scaling, Regimes, and Deviation
**Inputs:** outputs from Repo 2  
**Outputs:** expected scaling baselines and deviation surfaces  

---

## Repo 4 — Predictive Signals & Risk
**Inputs:** outputs from Repo 2 and Repo 3  
**Outputs:** predictive features and baseline models  

---

## Design Principle

Repos are:
- analytically sequential
- operationally independent
- reviewable in isolation

No circular dependencies are allowed.



