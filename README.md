# Tracking the Sun — Analytical Architecture

This repository does not contain analysis.  
It defines the conditions under which analysis is allowed to happen.

Tracking the Sun is treated here as a long-lived analytical object rather than a one-off dataset. The intent is to establish stable structure before questions are asked, so that downstream work does not diverge in assumptions, semantics, or validation logic.

This repository defines a **single trusted analytical substrate** that downstream repositories depend on. Schema decisions, column semantics, scope boundaries, and analytical constraints are declared here and inherited elsewhere.

---

## Architectural Framing

The NREL *Tracking the Sun* dataset spans more than two decades of distributed solar installations across the United States, beginning in the late 1990s and extending into the present.

Across that time horizon, installation practices, reporting standards, technologies, incentive structures, and market conditions change. Those changes are embedded in the data. If they are not explicitly accounted for, analytical results can conflate structurally different systems into patterns that appear coherent but are not analytically stable.

This architecture exists to control for that.

Rather than approaching the dataset as a single analytical surface, the work is decomposed into multiple repositories. Each repository is scoped around a specific class of questions, produces defined outputs, and passes those outputs forward without redefining assumptions.

Each repository must be internally coherent while remaining legible as part of the larger system.

---

## Repository Roles and Relationships

The architecture is organized as a sequence of repositories operating at distinct analytical layers. Repositories are related through dependency, not containment.

### Repo 1 — System Size Determinants

Establishes descriptive grounding.

This repository focuses on contextual, technical, and temporal factors associated with observed system size. Its outputs define baseline features and reference frames that are consumed by later repositories.

No predictive claims are made here.

---

### Repo 2 — System Configuration & Inverter Architecture

Builds on size-conditioned baselines defined in Repo 1.

This repository examines how systems of comparable size are configured in practice, with emphasis on inverter count, capacity allocation, and installer behavior as structural signals.

Outputs describe configuration patterns conditional on size and context and are passed forward unchanged.

---

### Repo 3 — Scaling, Regimes, and Deviation

Consumes baselines and configuration features defined in Repos 1 and 2.

This repository formalizes expected scaling behavior, identifies regime formation, and characterizes deviation across time and geography. The focus is on pattern structure rather than explanation.

Outputs define deviation surfaces and regime boundaries used downstream.

---

### Repo 4 — Predictive Signals, Risk, and Oversizing

Operates strictly within constraints established upstream.

This repository uses features defined earlier to explore deviation likelihood, directionality, and potential risk. Predictive work is bounded by prior definitions rather than introducing new interpretations of the data.

---

## Treatment of Time

Time is explicitly scoped per repository.

- In **Repo 1** and **Repo 2**, time functions as conditioning context. It is used for cohorting, comparison across periods, and framing descriptive baselines.
- In **Repo 3**, time is treated as an evolutionary signal, enabling identification of regime formation, persistence, and structural change.
- In **Repo 4**, time is introduced as a predictive feature, constrained by upstream definitions rather than reinterpreted.

This separation prevents descriptive patterns from being overstated as evolutionary claims or predictive signals without justification.

---

## The Analytical Substrate

The analytical substrate defined by this repository is conceptual rather than executable.

It consists of:
- validated schema decisions  
- consistent column semantics  
- documented assumptions and exclusions  

These are treated as contracts. Downstream repositories inherit them rather than re-validating raw data, unless explicitly stated otherwise. This keeps analytical effort focused on reasoning rather than repeated preprocessing.

Supporting material lives in the `docs/` directory and includes:
- data contracts  
- conventions  
- dataset overview  
- repository dependency definitions  

These documents define rules and constraints, not analysis.

---

## Scope Boundaries

This architecture is observational rather than causal.  
It prioritizes analytical reasoning over prescription.  
It is modular by design to support extension without structural breakage.

---

## Status

The architecture is under active development.

Structural decisions are stabilizing.  
Analytical content evolves within those constraints.




