# Analytical Conventions

This document defines shared conventions across the program.

---

## Notebook Philosophy

Notebooks are:
- readable analytical artifacts
- ordered narratives, not scripts
- explicit about inputs and outputs

Every notebook begins with a **Notebook Contract**.

---

## Printing & Visibility

All validation, filtering, and transformations:
- print shapes
- print summary statistics
- expose intermediate outputs

Silent transformations are avoided.

---

## Feature Engineering

Derived features:
- are additive, not destructive
- preserve original fields
- are saved explicitly for reuse

---

## Statistical Discipline

- Distributions before models
- Baselines before deviations
- Descriptive clarity before prediction

No notebook mixes:
- EDA
- modeling
- interpretation
without explicit separation.

---

## Language

Claims are:
- observational
- comparative
- conditional

Causal language is avoided unless explicitly justified.

---

## Audience

This program is written for:
- senior data analysts
- data scientists
- technically literate reviewers

Not for tutorials.
