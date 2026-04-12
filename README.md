# Andy Moran — Quantitative Researcher

My MPlan research at Manchester used Cuba's post-Soviet subsidy collapse, specifically modelling how Manchester's food system would respond to a comparable climate-driven shock, and what that implies for UK policy under energy crisis conditions. The research was interesting; the frustration was that its prescriptions couldn't be measured. I couldn't reconcile 'top-down' technocratic theory with ground-level reality. Rather than continue 'hallucinating' policies, I left the field to build things that had to work in the real world.

But my planning research remains relevant: Cuba is again experiencing severe energy constraints, and the system‑level responses echo the same dynamics I studied years ago. Those patterns appear today in the geopolitical volatility of the Strait of Hormuz, and this reinforced a core truth: uncertainty has a structural pattern that intuition alone cannot capture. Reading Annie Duke’s Thinking in Bets provided the necessary pivot: a move toward the formal probabilistic tools needed to reason honestly about real‑world risk.

I've now worked through the frequentist foundations and moved into Bayesian modelling. I've built projects that moved from "this seems straightforward" to "this is a lot more complicated than I thought" to "this model doesn't fit the data". I've iterated, failed, and actively invited criticism, because I want to get things right. 

My project, "Detecting False Signals in Mean-Reversion Models", used Premier League xG data as a case study. It started as a search for signal and ended as a lesson in how easily rolling means create artefacts. It didn't prove what I hoped. Instead, it provided a clear demonstration of how smoothing can create spurious signals that pass every standard test. I abandoned the signal because I care about ground truth, quick empirical feedback, and models that survive contact with data, not just persuade in slide decks. If the data disagrees with the model, the data wins. I’m interested in predictive power, not models that protect an expert’s reputation.

I'm now applying Bayesian modelling, regime-switching processes, causal inference, and structured null testing to GB electricity markets. The specific question: has the evening demand ramp already begun to change shape as EV adoption grows, and what is that structural shift worth to a storage asset before the forward curve prices it in?

# Current Focus

I’m building a curated, professional portfolio in energy‑sector: forecasting, risk modelling, and probabilistic optimisation. My work emphasises:

- clean, readable analysis

- principled statistical reasoning

- reproducible workflows

- uncertainty‑aware modelling

- clear narrative structure

- decision‑ready insights

# Connect

Actively exploring roles in energy trading, storage optimisation, and probabilistic modelling.
Available for informal coffee and chats. Interested in talking
to people working on storage optimisation, flexibility markets,
and DER price impact. Please explore the repositories. Brutal adversarial practitioner feedback welcome. Reach out here:
andrewgmoran@gmail.com


# Energy Projects

All energy projects are built around a common discipline: pre-register the stopping rule, report the null result, and stop when the data says stop.

| Project | Result | Methods |
|--------|--------|---------|
| [Causal Grid Signals](https://github.com/AndyMoran/grid-causal) | Detection confirmed (7/9 events, p = 0.008). Honest P&L negative. | CUSUM, Savitzky–Golay RoCoF, two‑regime attribution, Wilcoxon test |
| [Across the Water](https://github.com/AndyMoran/across-the-water) | Signal absorbed by IFA2 implicit coupling. Pre-registered DA hard gate failed at Model B. Market is efficient at this horizon. | Bayesian structural model, counterfactual simulation, ENTSO‑E data |
| [Ahead of the Curve](https://github.com/AndyMoran/ahead-of-the-curve) | Smart-charging signal not yet detectable. Revisit 2032 | Hierarchical Bayesian regression, feature ablation, NESO/Elexon data |
| [xG Spread Failure Model](https://github.com/AndyMoran/xg-spread-model) | xG spreads fail to predict match outcomes. | Logistic regression, calibration curves, posterior predictive checks |
| [VAR & Home Advantage](https://github.com/AndyMoran/var-home-advantage) | VAR reduces home advantage by ~20%. | Bayesian time‑varying model, causal attribution |
| [Cyclistic Bayesian Pricing](https://github.com/AndyMoran/cyclistic-bayesian-pricing) | Identified price‑sensitive segments. | Hierarchical Bayesian model, posterior clustering |
| [Falcon 9 Reliability](https://github.com/AndyMoran/falcon9) | Reliability >98% with narrowing uncertainty. | Bayesian survival analysis, hazard modelling |
| [Bellabeat Activity Modelling](https://github.com/AndyMoran/bellabeat) | Weak predictive signal; null result. | Random forest, feature engineering, cross‑validation |


## Causal Grid Signals — Can a GB forced generation outage be detected from 1-second frequency data and does it produce a tradeable intraday price premium?

**Result:** Detection confirmed (7/9 events, p = 0.008, median +£3.44/MWh). Honest P&L negative at −£31.31 on 1 MW. Edge lives in a sub-30-second execution window. 30-minute settlement data cannot measure. Strategy requires real-time BM stream and intraday tick feed to execute.

**Techniques:** CUSUM sequential detection, Savitzky-Golay RoCoF extraction, two-regime causal attribution (Regime_FastShock / Regime_SlowRamp), Wilcoxon signed-rank test, SBP-proxy P&L with explicit execution assumptions

**Focus:** whether the Rate of Change of Frequency in the first seconds after a grid event is sufficient to classify it, detect it within ±5 seconds of onset, and capture the resulting price dislocation with publicly available data 

**Repo:** https://github.com/AndyMoran/grid-causal

Demonstrates:

- physics-first calibration
- honest null result reporting
- explicit execution gap diagnosis
- full public data pipeline across NGET, Elexon, and NESO


## Across the Water — Does the GB day‑ahead market fully price French nuclear unplanned outage announcements?

**Result:** Signal absorbed by IFA2 coupling. Pre-registered DA hard gate failed at Model B. Market is efficient at this horizon.

**Techniques:** SCM causal identification, OLS panel regression with HAC standard errors, two-model specification (Model A / Model B), reduced-form IFA flow regression, pre-registered gate structure

**Focus:** testing whether unplanned French nuclear outage announcements produce a residual mispricing in GB day-ahead prices after IFA2 implicit coupling is accounted for

**Repo:** https://github.com/AndyMoran/across-the-water

GB imports electricity from France via IFA and IFA2 (~3 GW combined). When a French reactor trips unexpectedly, French export capacity falls and GB must dispatch more expensive domestic generation. The question is not whether outages affect prices — they do — but whether the market prices the information fast enough that no systematic DA edge remains.

The identification strategy uses a two-model SCM specification. Model A estimates the total causal effect of unplanned outages on GB DA prices, controlling for TTF gas spot, French temperature deviation, German wind, IFA flows, and season/year fixed effects. Model B adds the French DA clearing price (08:00 UTC) as a control, identifying the residual GB DA mispricing after IFA2 implicit coupling has transmitted the signal.

Model A passed all three gate conditions (β = £2.94/MWh per GW, p = 0.010, effect > £2/MWh/GW). Model B failed: conditioning on the FR DA clearing price collapses the estimated effect to −£0.41/MWh per GW (p = 0.677). The β drops by £3.35/MWh/GW — 114% of the Model A estimate — leaving a residual indistinguishable from zero. The project stops here by design.

The null result is precisely diagnosed: IFA2's implicit coupling algorithm uses the FR DA price to jointly optimise cross-border flows. By the time the GB DA auction clears at 11:00, the outage signal has already been fully transmitted via the FR DA clear at 08:00. Large energy desks with IFA2 pricing infrastructure have evidently incorporated this channel. The minimum detectable effect at hourly public data resolution is ~£1.5–2.0/MWh; a residual sub-hourly ID signal cannot be ruled out but requires tick-level data and co-located execution infrastructure to test.

Demonstrates:

- principled null-testing with a pre-registered two-stage gate — precise diagnosis, not just rejection
- SCM causal identification with explicit confounder structure and two parallel model specifications
- IFA1/IFA2 structural distinction and reduced-form interconnector flow regression
- backtest integrity via ENTSO-E fetch timestamp logging (notices sometimes filed retroactively)
- full public data pipeline across 10 sources — ENTSO-E, Elexon, NESO, RTE, open-meteo, Yahoo Finance
- pre-written unrun notebooks (03–06) published unmodified to demonstrate pre-registration discipline

## Ahead of the Curve — Detecting when EV smart‑charging affects the evening–overnight arbitrage spread

**Result:** Signal not detected. Pre-registered hard gate failed at Notebook 02. Revisit 2032.

**Techniques:** causal inference, DiD with high‑frequency controls, regime detection, diurnal shape analysis, battery dispatch modelling

**Focus:** detecting when EV smart‑charging begins to materially alter the evening–overnight arbitrage spread

**Repo:** https://github.com/AndyMoran/ahead-of-the-curve

GB's evening demand shape is shifting as EV adoption grows and smart‑charging mandates take effect. For a storage asset, the question is not whether the shape will change but when the change becomes large enough to affect the arbitrage spread, and what that shift is worth in NPV terms.

This project builds a detection framework for structural change in the GB evening ramp using Elexon half‑hourly settlement data, DVLA EV registrations, and NESO generation and demand data. The identification strategy uses the smart‑charging mandate as a quasi‑experimental treatment: its implementation date is unambiguous in a way that gradual adoption curves are not.

The pre-registered hard gate failed at Notebook 02. After controlling for wind forecast error, no residual chargepoint signal is detectable in GB day-ahead prices (wind-controlled Spearman ρ = −0.084, p = 0.575). The current shiftable load of ~1 GW sits below the detection threshold against ~1.4 GW of wind noise. The project stops here by design.

The null result is commercially useful: the smart charging effect is not yet priced into the spread distribution, and dispatch models require no adjustment today. The minimum detectable stock estimate (~12M compliant chargepoints, ~25 GW shiftable load) implies the signal will not be detectable until GB BEV stock approaches 8 million vehicles — projected around 2032–2035 on central adoption forecasts. The framework is ready to rerun at that point.

Demonstrates:

- principled null‑testing with a pre-registered hard gate — fail fast, move on
- structural‑change detection in noisy, confounded markets
- causal inference with high‑frequency controls (wind forecast error, interconnectors, demand)
- sunset‑adjusted diurnal window construction
- minimum detectable effect estimation and revisit threshold quantification

## xG Spread Failure Model — Null‑Model Calibration & False‑Signal Detection

**Result:** Rolling mean spreads can deceive. Check early for Null.

**Techniques:** Bayesian modelling, posterior predictive simulation, null‑model construction

**Focus:** Detecting when rolling‑mean “signals” are artefacts rather than genuine effects.

**Repo:** https://github.com/AndyMoran/xg-spread-model

This project started as a search for signal and ended as a sober lesson. The result a Bayesian failure‑mode analysis showing how rolling‑mean spreads in football xG data can produce convincing‑looking patterns even when no real effect exists. The model builds a principled null distribution, simulates thousands of fake seasons, and compares the observed statistic against that null to quantify whether the pattern is real or an artefact of autocorrelation and variance instability.

Demonstrates:

- principled null‑model construction

- posterior predictive simulation for false‑positive detection

- diagnosing artefacts in rolling‑window time‑series models

- clear communication of uncertainty and model limitations

# Machine learning and data science projects

## VAR and Premier League Home Advantage: A Bayesian Analysis

Techniques: Bayesian modelling, sensitivity analysis, segmentation, causal reasoning

Focus: Evaluating VAR’s impact on competitive balance

Repo: https://github.com/AndyMoran/var_home_advantage_bayesian_analysis

A Bayesian investigation into whether VAR changed home advantage. Includes a full convergence section, PPCs, model justification, and a Big Six vs others segmentation. Sensitivity analysis shows that pandemic crowd‑effects, not VAR, explain most of the apparent shift.

Demonstrates:

- principled Bayesian inference

- sensitivity analysis to identify confounding

- segmentation for competitive‑balance evaluation

- translating statistical findings into business‑ready insights

## Cyclistic Bayesian Pricing & Behaviour Simulation

**Techniques:** Monte Carlo simulation, Bayesian decision‑making, scenario analysis

**Focus:** Pricing strategy under uncertainty

**Repo:** https://github.com/AndyMoran/Cyclistic_bayesian_analysis

A simulation‑based pricing model exploring how fare changes affect rider behaviour and revenue. Includes full convergence diagnostics, PPCs, and a clear justification for the modelling structure. Quantifies risk, identifies robust strategies, and supports policy decisions.

Demonstrates:

- simulation‑based decision‑making

- modelling behavioural uncertainty

- evaluating pricing trade‑offs probabilistically

## Falcon 9 Bayesian Reliability Analysis

Techniques: Bayesian logistic regression, calibration, validation

Focus: Engineering reliability & economic decision‑making

Repo: https://github.com/AndyMoran/falcon9-bayesian-reliability-analysis

A Bayesian model estimating Falcon 9 booster landing reliability across missions, pads, and rocket versions. Includes full convergence diagnostics, posterior predictive checks, and calibration/ROC validation. Extends into expected‑value economics to quantify the financial return of reusability under uncertainty.

Demonstrates:

- hierarchical reliability modelling

- uncertainty‑aware engineering decisions

- combining inference with economic reasoning

## Bellabeat Bayesian Activity Modelling

**Techniques:** Gamma likelihood, Fourier circadian modelling, hierarchical structure

**Focus:** Behavioural segmentation & personalised engagement

**Repo:** https://github.com/AndyMoran/bellabeat_bayesian_analysis

A hierarchical Gamma/Fourier model capturing 24‑hour activity rhythms across Bellabeat personas. Includes model comparison (WAIC/LOO), full diagnostics, and literature integration on circadian modelling. Uses probability‑of‑superiority to compare personas hour‑by‑hour.

Demonstrates:

- modelling cyclic behaviour with Fourier series

- principled handling of right‑skewed data

- uncertainty‑aware behavioural comparison

# Learning Portfolio (Completed Courses)

**Techniques:** Data cleaning, wrangling, visualisation, structured reporting

**Focus:** Foundations & breadth

**Repo:** https://github.com/AndyMoran/learning-portfolio

A curated collection of projects from the Google Data Analytics and IBM Data Science programmes. Cleaned, organised, and documented to demonstrate foundational analytical skills and clear communication.

# Core Skills

- Bayesian modelling (PyMC, ArviZ)

- Monte Carlo simulation & scenario analysis

- Python (pandas, numpy, matplotlib, seaborn, scikit‑learn)

- R (tidyverse, ggplot2)

- SQL

- Data cleaning, wrangling, and visualisation

- Clear technical writing and structured reporting

# What I'm Working On

- Expanding into energy‑sector probabilistic modelling

- Strengthening my Bayesian and simulation workflows

- Building messy‑data projects using probabilistic forests and market‑maker models

- Continuing to refine the clarity and structure of my analytical writing

## Learning & Growth

- Completing Luis Serrano’s Math for Machine Learning to ensure technical depth
  
- Mathematics for Machine Learning, Imperial

- Expanding into energy‑sector forecasting and risk modelling


