# Andy Moran

## Applied Data Scientist & Quantitative Modeller  
### Energy Systems · Infrastructure Analytics · Physics-First Simulation · Decision-Making Under Uncertainty

I build reproducible analytical projects that turn messy real-world operational data into structured evidence, quantitative models and decision-ready insight.

My current focus is GB electricity markets and energy-system transition: storage, flexibility, constraints, VPPs, LDES, curtailment, locational value and market-design incentives.

The wider theme is broader than energy:

> **How do complex infrastructure systems behave under stress, and what decisions become possible when the data is cleaned, structured, modelled and explained properly?**

My work combines:

- data engineering;
- physical system modelling;
- economic and financial modelling;
- Monte Carlo simulation;
- uncertainty analysis;
- event detection;
- causal discipline;
- technical communication;
- policy-facing interpretation.

Before returning to applied quantitative work, I worked as a Principal Technical Writer at Oracle, translating complex enterprise software into clear documentation, setup manuals, in-product text and user-facing guidance. That background still shapes how I work: models should not just run; they should be inspectable, explainable and useful.

---

## Current Research Programme

My projects are built around a common workflow:

messy operational data
→ reproducible pipeline
→ physical/event model
→ economic or policy interpretation
→ uncertainty / sensitivity testing
→ decision-ready output

The energy work currently falls into four connected themes:

1. Long-duration storage economics
How duration, location, technology and financing structure affect support needs.
2. Constraint and balancing-market analytics
How real system stress appears in BM actions, BOALF data and regional dispatch.
3. Distributed flexibility and VPP value
Whether domestic batteries are actually available at event time, once consumer constraints are respected.
4. Strategic demand siting
How new large loads, including AI infrastructure, should be evaluated against constraint direction, renewable absorption and residual grid burden.

---

## Selected Projects

**Ofgem LDES Window 1 Modelling**

Formal consultation response and supporting analysis for Ofgem’s Long-Duration Electricity Storage cap-and-floor Window 1 process.

The work examined how support calibration changes when project economics differ by:

- duration;
- technology;
- location;
- constraint exposure;
- TNUoS assumptions;
- degradation;
- financing structure;
- asset lifetime.

Key themes:

- long-duration Li-ion and pumped hydro are not interchangeable;
- single national duration curves risk hiding locational and technology-specific economics;
- constrained locations can face materially different revenue sufficiency;
- project finance assumptions can change apparent floor-support needs dramatically.

Methods used:

- project-level revenue modelling;
- Monte Carlo simulation;
- project-finance analysis;
- duration sensitivity;
- technology comparison;
- policy interpretation;
- reproducible Python/Jupyter workflows.

LDES Window 1 Modelling — https://github.com/AndyMoran/ldes-window1-modelling

---

## Tenant-Safe VPP Flexibility Accreditation

A modelling framework for estimating how much domestic battery capacity is genuinely available to the grid once household and tenant needs are protected.

The project asks:

> How much of a domestic battery fleet can be safely accredited as grid flexibility when heating, comfort, reserve floors, opt-outs and cold-weather stress are respected?

Core idea:

Installed capacity is visible.
Tenant-safe flexibility is not.

The model distinguishes between:

- nameplate battery capacity;
- simulated household-level availability;
- thermal derating;
- phase imbalance;
- communications availability;
- primacy / opt-out behaviour;
- cold-spell stress;
- tenant reserve floors.

The result is a **Tenant-Safe Flexibility Factor** rather than a simple nameplate assumption.

This is designed for VPPs, social housing, domestic battery fleets, DNO/NESO flexibility products and consumer-protection-aware grid services.

Tenant‑Safe VPP Flexibility — https://github.com/AndyMoran/tenant-safe-vpp-flexibility

---

## South West Domestic Battery VPP Model

A public-data demonstrator testing whether domestic batteries in the South West can provide event-time locational flexibility value.

The core question:

> When the grid is stressed, is a domestic VPP in the right state of charge, at the right time, moving power in the right direction?

The work compares:

- national price-following dispatch;
- household-only optimisation;
- perfect oracle constraint response;
- realistic consumer-constrained VPP dispatch.

Key concept:

A useful VPP must be:
1. in the right place;
2. at the right time;
3. with enough state of charge;
4. moving power in the right direction.

This project links wholesale price signals, local constraint value, consumer behaviour and event-time deliverability.

South West Domestic Battery VPP — https://github.com/AndyMoran/sw-vpp-domestic-battery

## South West Constraint Modelling

Analysis of regional constraint behaviour in the South West using Elexon BOALF and Balancing Mechanism data.

The project reconstructs contiguous constraint-relevant events from operational dispatch data to test whether South West flexibility value is visible at transmission-system scale.

Key finding direction:

- South West constraint value is not purely a winter evening import-stress story;
- Summer and Autumn event structures matter;
-- distributed flexibility value depends strongly on timing, direction and local system state.

Methods used:

- BOA/BOALF joins;
- event reconstruction;
- settlement-period timestamp handling;
- VWAP accepted-price metrics;
- regional BMU classification;
- seasonal event analysis.

South West Constraint Modelling — https://github.com/AndyMoran/sw-restraint-modelling

---

## Scotland AI Split-Zones

A proposed training/inference siting framework for grid-constrained Scotland.

The project starts from a simple observation:

> AI compute is not one thing.

Large-model training, real-time inference, batch inference and edge AI have different power, latency and flexibility characteristics. They should not automatically be sited in the same places or judged by the same grid criteria.

Core thesis:

Flexible AI training load may belong near trapped renewable power.
Latency-sensitive inference may belong near users and fibre.
Tenant-safe VPPs may help at the margin, but they are not baseload substitutes for hyperscale AI.

The project evaluates sites by:

- constraint direction;
- renewable absorption value;
- residual grid burden;
- workload flexibility;
- fibre / latency suitability;
- tenant-safe VPP support;
- planning and local impact.

This extends the VPP work into strategic demand siting and infrastructure policy.

Scotland AI Split‑Zones — https://github.com/AndyMoran/scotland-ai-split-zones 

---

## Methods and Tools

**Data Engineering**
- Python
- Polars
- DuckDB
- Pandas where appropriate
- Parquet-first workflows
- schema validation
- reproducible data pipelines
- public operational datasets
- messy time-series cleaning
- settlement-period alignment

**Modelling**

- physical system modelling
- event detection
- battery dispatch simulation
- Monte Carlo simulation
- state-transition models
- revenue sufficiency testing
- project-finance modelling
- sensitivity analysis
- scenario comparison
- adversarial validation

**Analytical Discipline**

- physics-first assumptions;
- no hidden time travel;
- no leakage in non-stationary markets;
- explicit stopping rules;
- null results reported plainly;
- model simplicity before complexity;
- uncertainty before false precision;
- charts that explain rather than decorate.

---

**Project Philosophy**

My work is specification-led and evidence-led.

I try to avoid building models that simply confirm the preferred answer. The process is closer to:

model result
→ discomfort
→ mechanism
→ sensitivity
→ policy or commercial implication
→ caveat

A good model should survive awkward questions:

- What information was available at decision time?
- What has been assumed but not measured?
- What breaks in the stress case?
- Is the result driven by physics, economics or a convenient multiplier?
- Could the opposite conclusion also be supported by the same data?
- Is this genuine insight, or spreadsheet cosplay wearing a hard hat?

The last one is not a formal validation test, but perhaps it should be.

## Why GitHub?

Each project is treated as a research product, not just a notebook dump.

A good project should include:

- clear research question;
- documented data sources;
- reproducible environment;
- explicit assumptions;
- clean pipeline structure;
- versioned outputs;
- figures;
- interpretation;
- limitations;
- next-step questions.

The aim is to make the analysis inspectable by technical readers, policy readers and commercial stakeholders.

## Current Direction

I am now looking to bring this combination of data engineering, physical modelling, economic analysis, uncertainty modelling and technical communication into paid analytical, consultancy or research roles.

Areas of particular interest:

- energy systems;
- storage and flexibility;
- VPPs;
- grid constraints;
- LDES;
- strategic demand connection;
- infrastructure resilience;
- emergency-response analytics;
- public-interest data science;
- decision support under uncertainty.

---

**Contact**

Email: andrewgmoran@gmail.com

GitHub:[github.com/AndyMoran
](https://github.com/AndyMoran)

LinkedIn: www.linkedin.com/in/andy-graham-moran/

### Deep Dive
Here be Dragons. If you want the full modelling philosophy, project deep dives, and research notes, see the:  
[Energy Modelling Deep Dive](./deep-dive/energy-modelling.md)
