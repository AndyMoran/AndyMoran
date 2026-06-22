# Andy Moran — Quantitative Researcher

**Physics‑first signal detection for GB electricity markets. Transparent reporting, nulls included.**

I build physics‑first signal‑detection pipelines, walk‑forward models, and structured null tests for GB electricity markets. All results, including nulls, are reported transparently.

My background spans urban systems modelling (MPlan, Manchester), Bayesian inference, and structured decision‑making under uncertainty. I moved from planning research into energy markets to work on problems where intuition fails and only disciplined modelling provides traction.

I’ve completed six energy‑market studies using public BM, NESO, and ENTSO‑E data. Each project follows the same principle: use the simplest model that works, apply machine learning only when it adds genuine explanatory or predictive value, and report results honestly. My work includes constraint behaviour, outage detection, implicit coupling, smart‑charging signals, adaptive fair‑value modelling, and walk‑forward equilibrium estimation for GB balancing spreads.

---

## Current Research

### Project B — Grid Connection Arbitrage & Hybrid Flexibility Economics (Active)

A new research programme exploring whether hybrid BESS–renewable configurations can bypass the grid‑connection queue and unlock viable flexibility economics.

Focus areas:

- connection‑queue arbitrage

- co‑location with curtailed renewable generation

- hybrid asset revenue stacking

- curtailment‑driven opportunity formation

- system‑level implications for flexibility deployment

This project extends the Physics Before Economics approach into the emerging frontier of hybrid flexibility and connection‑constrained development.

### Completed — GB Constraint Analytics Platform

A three‑part analytical framework evaluating GB transmission constraints, storage feasibility, and constraint‑relief economics. 

https://github.com/AndyMoran/GB-Constraint-Analytics-Platform

**Key results:**

- Constraint burden is highly concentrated in a small number of North‑West boundaries. 

- A 50 MW / 4 h BESS captures only ~1.7% of total system constraint opportunity.

- Constraint‑management revenues cover <5% of basic operating costs.

- A 10,000‑iteration Monte Carlo simulation shows a 0.00% probability of standalone viability.

- Findings remain robust under extensive pricing, attribution, and sensitivity testing.

**Conclusion:**

Constraint revenue is structurally insufficient to support standalone storage investment; it functions only as a marginal top‑up.

**Project structure:**

The platform enforces institutional‑grade analytical discipline:

- Modular Architecture — shared logic (DCF engines, validators, cost models) isolated in src/.

- Data Contracts — schema, row‑count, and physical‑plausibility checks at every stage.

- Automated Testing — core economic engines validated with pytest and mocked fixtures.

- Adversarial Review — explicit checks for unit consistency, threshold justification, and leakage.

Part I — Data Platform (NB01–NB07)  
Ingestion, validation, harmonisation, and construction of constraint‑ready analytical datasets.

Part II — Constraint Behaviour & Storage Feasibility (NB08–NB12)  
GB‑wide screening of persistence, burden, clustering, and operational archetypes, plus a detailed North‑West case study.

Part III — Constraint Economics & System‑Level Value (NB13–NB18)  
Opportunity valuation, physical revenue capture, 15‑year DCF viability, and Monte Carlo robustness analysis.

---

### Current Areas of Focus

| Topic | Current Direction |
| --- | --- |
| **Market‑state detection** | Identifying persistent stress regimes from imbalance spreads |
| **Constraint persistence** | Assessing whether physical bottlenecks create repeatable market conditions |
| **Duration suitability** | Comparing short‑ vs long‑duration storage under real persistence characteristics |
| **Methodology** | Walk‑forward evaluation, train/test separation, leakage prevention, reproducible notebook design |

### Research Approach

Projects are specification‑led, not notebook‑led.

Each project begins with:

- a README (research framing)

- project.md (operational rules)

- explicit stopping criteria

- reproducibility requirements

- walk‑forward or out‑of‑sample evaluation where appropriate

- methodology.md

Emphasis is placed on disciplined validation, transparent reporting of null results, and avoiding leakage in non‑stationary market environments.

A growing focus is the construction of reproducible analytical datasets from fragmented real‑world infrastructure sources — timestamp reconciliation, API‑ingestion validation, schema standardisation, and cross‑system alignment.
Data engineering, QA, and reproducibility are treated as core components of the research process rather than preprocessing steps.

---

# Connect

I’m exploring roles in energy trading, storage optimisation, and probabilistic modelling. Open to informal coffee chats, especially with people working on:

- storage optimisation & flexibility markets  
- DER price impact  
- grid‑scale battery dispatch & constraint modelling  

Brutal adversarial practitioner feedback welcome.

Reach out: andrewgmoran@gmail.com

# Energy Projects

All energy projects are built around a common discipline: pre-register the stopping rule, report the null result, and stop when the data says stop.

| Project | Result | Methods |
|--------|--------|---------|
| [Walk‑Forward Adaptive Fair‑Value Modelling](https://github.com/AndyMoran/bm-adaptive-fair-value) | Walk‑forward equilibrium model tracks non‑stationary BM spreads. Static models overstate residual stress; adaptive retraining reduces false dislocations and stabilises fair‑value estimates. | Walk‑forward retraining, residual stress diagnostics, equilibrium drift estimation, XGBoost, rolling feature engineering, timestamp‑aligned BM spread construction |
| [South West Constraint Modelling](https://github.com/AndyMoran/sw-restraint-modelling) | Region-specific constraint behaviour diverges from system-level patterns. Wind shows weak or negative relationship with constraints; risk is structurally non-linear but low in magnitude (~3%). | Settlement-period alignment, BM volume construction, percentile-based event definition, logistic regression, random forest (non-linear structure), empirical validation |
| [Overnight Recharge](https://github.com/AndyMoran/project-f-overnight-recharge) | Economic null. Causal design fails (HS-3). Controlled effect (−£4.7/MWh, p≈0.05) is statistically fragile and non-monetisable. | Pre-registration, matched-pairs, HS gates, regression, OVB (sign reversal), execution-aware P&L |
| [Causal Grid Signals](https://github.com/AndyMoran/grid-causal) | Detection confirmed (7/9 events, p = 0.008). Honest P&L negative. | CUSUM, Savitzky–Golay RoCoF, two‑regime attribution, Wilcoxon test |
| [Across the Water](https://github.com/AndyMoran/across-the-water) | Signal absorbed by IFA2 implicit coupling. Pre-registered DA hard gate failed at Model B. Market is efficient at this horizon. | SCM causal identification, OLS with HAC standard errors, pre-registered two-stage gate. |
| [Ahead of the Curve](https://github.com/AndyMoran/ahead-of-the-curve) | Smart-charging signal not yet detectable. Revisit 2032 | DiD with high-frequency controls, structural change detection, diurnal shape analysis. |

### Walk‑Forward Adaptive Fair‑Value Modelling for GB Balancing Spreads — Does adaptive retraining stabilise equilibrium estimates under non‑stationarity?

**Result:**  
Static equilibrium models overstate residual stress and misidentify dislocations when applied to non‑stationary BM spreads. A walk‑forward adaptive model — retrained on each step using only past information — produces materially more stable fair‑value estimates, reduces false positives, and tracks equilibrium drift without leaking future structure. Residual stress collapses under walk‑forward evaluation: large “dislocations” seen in static backtests are revealed as artefacts of look‑ahead bias and structural drift rather than genuine market mispricing.

**Conclusion:**  
Adaptive retraining is essential for fair‑value modelling in the BM. Static models systematically exaggerate stress; walk‑forward methods recover a stable, low‑noise equilibrium and eliminate spurious signals.

**Techniques:**  
Walk‑forward retraining · timestamp‑aligned BM spread construction · rolling feature engineering · XGBoost regression · residual stress diagnostics · equilibrium drift estimation · out‑of‑sample validation

**Focus:**  
Whether fair‑value estimates for BM spreads remain stable when evaluated under strict walk‑forward discipline. The project tests whether static models genuinely detect stress or simply overfit structural drift, and whether adaptive retraining can recover a consistent equilibrium signal. It evaluates residual behaviour, dislocation frequency, and equilibrium stability under both static and walk‑forward regimes, isolating the contribution of non‑stationarity to apparent market stress.

**Repo:**  
https://github.com/AndyMoran/bm-adaptive-fair-value (github.com in Bing)

**Demonstrates:**

- disciplined walk‑forward modelling with no future leakage

- correct construction of timestamp‑aligned BM spreads

- identification of structural drift vs genuine dislocations

- reduction of false stress signals through adaptive retraining

- robust residual diagnostics under non‑stationarity

- clear separation of static backtest artefacts from true equilibrium behaviour

- honest reporting of when static intuition fails under real‑time constraints



### South West Constraint Modelling — Do system‑level wind–constraint relationships hold regionally?

**Result:**
System‑level analysis shows a strong positive relationship between wind generation and constraint probability (rising from ~3% to ~11%, a ~3× increase). However, this relationship does not generalise to the South West. Regional constraint events remain rare (~3%), show a weak or slightly negative relationship with wind, and exhibit only modest non‑linear structure. Random Forest models detect interaction effects between wind and demand, but empirical validation shows these effects are small and do not materially elevate risk.

**Conclusion:** regional constraint behaviour diverges from system‑level patterns; effect sizes are low.

**Techniques:**  
Settlement‑period alignment · BM volume construction · percentile‑based event definition · logistic regression · interaction modelling · Random Forest (non‑linear structure) · partial dependence analysis · empirical validation

**Focus:**  
Whether the system‑level relationship between wind generation and constraint risk — a clear, monotonic increase — also appears in the South West region. The project tests whether regional constraint events can be explained by wind, demand, or their interaction, and whether non‑linear structure meaningfully elevates risk across operating conditions.

**Repo:**  
https://github.com/AndyMoran/sw-restraint-modelling

**Demonstrates:**
- clean construction of a complete settlement‑period dataset (17,520 SPs)

- correct use of percentile‑based thresholds for regional BM activity

- disciplined comparison of system‑level vs regional behaviour

- identification of non‑linear structure without over‑interpreting weak signals

- empirical validation via binned heatmaps to avoid model hallucination

- honest reporting of low‑magnitude effects and region‑specific dynamics

- clear articulation of when system‑level intuition fails at regional scale

- extraction of a simple three‑regime “rule of thumb”: a 26% no‑risk zone (low wind, low demand), an 8% elevated‑risk zone (high wind, high demand, ~ 4.8% event rate), and a neutral baseline (~ 3.1% event rate) showing that constraint risk is fundamentally state‑dependent rather than monotonic in wind alone

### Overnight Recharge — Does BESS depletion suppress GB overnight prices?

**Result:**
The pre-registered matched-pairs design failed a hard-stop validity check (HS-3: insufficient overlap), preventing causal inference.
Post-lock regression and trading analysis find a weak negative relationship between depletion and overnight prices (~−£4.7/MWh per 10pp), but the estimate is statistically fragile (p ≈ 0.05), unstable across specifications, and not economically viable after realistic trading frictions.

**Conclusion:** economic null.

**Techniques:**
Matched-pairs design · HS-series validity gates · regression with controls · omitted variable bias identification (sign reversal) · signal construction · execution-aware P&L attribution

**Focus:**
Whether large-scale evening discharge of short-duration (≤2h) GB battery storage creates a measurable and monetisable “recharging footprint” in overnight imbalance prices, and whether this effect survives causal identification and realistic trading constraints.

**Repo:**
https://github.com/AndyMoran/project-f-overnight-recharge

**Demonstrates:**
- strict pre-registration discipline (v3.2 locked before data access)
- correct invalidation of a failed causal design (HS-3)
- clear separation of pre-registered vs post-lock analysis
- identification of omitted variable bias via sign reversal
- translation of statistical results into realistic trading P&L
- end-to-end construction of a usable dataset from complex Elexon / NESO sources
- honest reporting of a non-tradable result

### Causal Grid Signals — Can a GB forced generation outage be detected from 1-second frequency data and does it produce a tradeable intraday price premium?

**Result:** Detection confirmed (7/9 events, p = 0.008, median +£3.44/MWh). Honest P&L negative at −£31.31 on 1 MW. Edge lives in a sub-30-second execution window. 30-minute settlement data cannot detect measure. Strategy requires real-time BM stream and intraday tick feed to execute.

**Techniques:** CUSUM sequential detection, Savitzky-Golay RoCoF extraction, two-regime causal attribution (Regime_FastShock / Regime_SlowRamp), Wilcoxon signed-rank test, SBP-proxy P&L with explicit execution assumptions

**Focus:** whether the Rate of Change of Frequency in the first seconds after a grid event is sufficient to classify it, detect it within ±5 seconds of onset, and capture the resulting price dislocation with publicly available data 

**Repo:** https://github.com/AndyMoran/grid-causal

**Demonstrates:**

- physics-first calibration
- honest null result reporting
- explicit execution gap diagnosis
- full public data pipeline across NGET, Elexon, and NESO


### Across the Water — Does the GB day‑ahead market fully price French nuclear unplanned outage announcements?

**Result:** Signal absorbed by IFA2 coupling. Pre-registered DA hard gate failed at Model B. Market is efficient at this horizon.

**Techniques:** SCM causal identification, OLS panel regression with HAC standard errors, two-model specification (Model A / Model B), reduced-form IFA flow regression, pre-registered gate structure

**Focus:** testing whether unplanned French nuclear outage announcements produce a residual mispricing in GB day-ahead prices after IFA2 implicit coupling is accounted for

**Repo:** https://github.com/AndyMoran/across-the-water

GB imports electricity from France via IFA and IFA2 (~3 GW combined). When a French reactor trips unexpectedly, French export capacity falls and GB must dispatch more expensive domestic generation. The question is not whether outages affect prices — they do — but whether the market prices the information fast enough that no systematic DA edge remains.

The identification strategy uses a two-model SCM specification. Model A estimates the total causal effect of unplanned outages on GB DA prices, controlling for TTF gas spot, French temperature deviation, German wind, IFA flows, and season/year fixed effects. Model B adds the French DA clearing price (08:00 UTC) as a control, identifying the residual GB DA mispricing after IFA2 implicit coupling has transmitted the signal.

Model A passed all three gate conditions (β = £2.94/MWh per GW, p = 0.010, effect > £2/MWh/GW). Model B failed: conditioning on the FR DA clearing price collapses the estimated effect to −£0.41/MWh per GW (p = 0.677). The β drops by £3.35/MWh/GW — 114% of the Model A estimate — leaving a residual indistinguishable from zero. The project stops here by design.

The null result is precisely diagnosed: IFA2's implicit coupling algorithm uses the FR DA price to jointly optimise cross-border flows. By the time the GB DA auction clears at 11:00, the outage signal has already been fully transmitted via the FR DA clear at 08:00. Large energy desks with IFA2 pricing infrastructure have evidently incorporated this channel. The minimum detectable effect at hourly public data resolution is ~£1.5–2.0/MWh; a residual sub-hourly ID signal cannot be ruled out but requires tick-level data and co-located execution infrastructure to test.

**Demonstrates:**

- principled null-testing with a pre-registered two-stage gate — precise diagnosis, not just rejection
- SCM causal identification with explicit confounder structure and two parallel model specifications
- IFA1/IFA2 structural distinction and reduced-form interconnector flow regression
- backtest integrity via ENTSO-E fetch timestamp logging (notices sometimes filed retroactively)
- full public data pipeline across 10 sources — ENTSO-E, Elexon, NESO, RTE, open-meteo, Yahoo Finance
- pre-written unrun notebooks (03–06) published unmodified to demonstrate pre-registration discipline

### Ahead of the Curve — Detecting when EV smart‑charging affects the evening–overnight arbitrage spread

**Result:** Signal not detected. Pre-registered hard gate failed at Notebook 02. Revisit 2032.

**Techniques:** causal inference, DiD with high‑frequency controls, regime detection, diurnal shape analysis, battery dispatch modelling

**Focus:** detecting when EV smart‑charging begins to materially alter the evening–overnight arbitrage spread

**Repo:** https://github.com/AndyMoran/ahead-of-the-curve

GB's evening demand shape is shifting as EV adoption grows and smart‑charging mandates take effect. For a storage asset, the question is not whether the shape will change but when the change becomes large enough to affect the arbitrage spread, and what that shift is worth in NPV terms.

This project builds a detection framework for structural change in the GB evening ramp using Elexon half‑hourly settlement data, DVLA EV registrations, and NESO generation and demand data. The identification strategy uses the smart‑charging mandate as a quasi‑experimental treatment: its implementation date is unambiguous in a way that gradual adoption curves are not.

The pre-registered hard gate failed at Notebook 02. After controlling for wind forecast error, no residual chargepoint signal is detectable in GB day-ahead prices (wind-controlled Spearman ρ = −0.084, p = 0.575). The current shiftable load of ~1 GW sits below the detection threshold against ~1.4 GW of wind noise. The project stops here by design.

The null result is commercially useful: the smart charging effect is not yet priced into the spread distribution, and dispatch models require no adjustment today. The minimum detectable stock estimate (~12M compliant chargepoints, ~25 GW shiftable load) implies the signal will not be detectable until GB BEV stock approaches 8 million vehicles — projected around 2032–2035 on central adoption forecasts. The framework is ready to rerun at that point.

**Demonstrates:**

- principled null‑testing with a pre-registered hard gate — fail fast, move on
- structural‑change detection in noisy, confounded markets
- causal inference with high‑frequency controls (wind forecast error, interconnectors, demand)
- sunset‑adjusted diurnal window construction
- minimum detectable effect estimation and revisit threshold quantification

# Premier League Data Analytics

Evidence‑driven investigations into how the Premier League works. Do expected goals predict match outcomes? Did VAR reshape home advantage? Each project answers a specific football question with data, modelling, and clear results.

| Project | Result | Methods |
|--------|--------|---------|
| [xG Spread Failure Model](https://github.com/AndyMoran/xg-spread-model) |  Expected Goals (xG) spreads do **not** behave like a mean‑reverting financial spread and fail to predict match outcomes.| Logistic regression, calibration curves, posterior predictive checks. |
| [VAR & Home Advantage](https://github.com/AndyMoran/var-home-advantage) | VAR reduces home advantage by ~20%. | Bayesian time‑varying model, causal attribution |

### xG Spread Failure Model — Null‑Model Calibration & False‑Signal Detection

**Result:** Signal identified as smoothing artefact. Rolling mean spreads fail every out-of-sample test once null distribution is properly specified

**Techniques:** Bayesian modelling, posterior predictive simulation, null‑model construction

**Focus:** Detecting when rolling‑mean “signals” are artefacts rather than genuine effects.

**Repo:** https://github.com/AndyMoran/xg-spread-model

This project started as a search for signal and ended as a sober lesson. The result a Bayesian failure‑mode analysis showing how rolling‑mean spreads in football xG data can produce convincing‑looking patterns even when no real effect exists. The model builds a principled null distribution, simulates thousands of fake seasons, and compares the observed statistic against that null to quantify whether the pattern is real or an artefact of autocorrelation and variance instability.

**Demonstrates:**

- principled null‑model construction

- posterior predictive simulation for false‑positive detection

- diagnosing artefacts in rolling‑window time‑series models

- clear communication of uncertainty and model limitations

### VAR and Premier League Home Advantage: A Bayesian Analysis

**Techniques:** Bayesian modelling, sensitivity analysis, segmentation, causal reasoning

**Focus:** Evaluating VAR’s impact on competitive balance

**Repo:** https://github.com/AndyMoran/var_home_advantage_bayesian_analysis

A Bayesian investigation into whether VAR changed home advantage. Includes a full convergence section, PPCs, model justification, and a Big Six vs others segmentation. Sensitivity analysis shows that pandemic crowd‑effects, not VAR, explain most of the apparent shift.

**Demonstrates:**

- principled Bayesian inference

- sensitivity analysis to identify confounding

- segmentation for competitive‑balance evaluation

- translating statistical findings into business‑ready insights


# Probabilistic Modelling

The methods below use hierarchical Bayesian inference, simulation-based decision-making, and reliability modelling.

| Project | Result | Methods |
|--------|--------|---------|
| [Cyclistic Bayesian Pricing](https://github.com/AndyMoran/cyclistic-bayesian-pricing) | Identified price‑sensitive segments. | Hierarchical Bayesian model, posterior clustering |
| [Falcon 9 Reliability](https://github.com/AndyMoran/falcon9) | Reliability >98% with narrowing uncertainty. | Bayesian survival analysis, hazard modelling |
| [Bellabeat Activity Modelling](https://github.com/AndyMoran/bellabeat) | Weak predictive signal; null result. | Random forest, feature engineering, cross‑validation |

### Cyclistic Bayesian Pricing & Behaviour Simulation

**Techniques:** Monte Carlo simulation, Bayesian decision‑making, scenario analysis

**Focus:** Pricing strategy under uncertainty

**Repo:** https://github.com/AndyMoran/Cyclistic_bayesian_analysis

A simulation‑based pricing model exploring how fare changes affect rider behaviour and revenue. Includes full convergence diagnostics, PPCs, and a clear justification for the modelling structure. Quantifies risk, identifies robust strategies, and supports policy decisions.

**Demonstrates:**

- simulation‑based decision‑making

- modelling behavioural uncertainty

- evaluating pricing trade‑offs probabilistically

### Falcon 9 Bayesian Reliability Analysis

Techniques: Bayesian logistic regression, calibration, validation

Focus: Engineering reliability & economic decision‑making

Repo: https://github.com/AndyMoran/falcon9-bayesian-reliability-analysis

A Bayesian model estimating Falcon 9 booster landing reliability across missions, pads, and rocket versions. Includes full convergence diagnostics, posterior predictive checks, and calibration/ROC validation. Extends into expected‑value economics to quantify the financial return of reusability under uncertainty.

Demonstrates:

- hierarchical reliability modelling

- uncertainty‑aware engineering decisions

- combining inference with economic reasoning

### Bellabeat Bayesian Activity Modelling

**Techniques:** Gamma likelihood, Fourier circadian modelling, hierarchical structure

**Focus:** Behavioural segmentation & personalised engagement

**Repo:** https://github.com/AndyMoran/bellabeat_bayesian_analysis

A hierarchical Gamma/Fourier model capturing 24‑hour activity rhythms across Bellabeat personas. Includes model comparison (WAIC/LOO), full diagnostics, and literature integration on circadian modelling. Uses probability‑of‑superiority to compare personas hour‑by‑hour.

**Demonstrates:**

- modelling cyclic behaviour with Fourier series

- principled handling of right‑skewed data

- uncertainty‑aware behavioural comparison

# Core Skills

- Bayesian modelling (PyMC, ArviZ)

- Monte Carlo simulation & scenario analysis

- Python (pandas, numpy, matplotlib, seaborn, scikit‑learn)

- R (tidyverse, ggplot2)

- SQL

- Data cleaning, wrangling, and visualisation

- Clear technical writing and structured reporting
