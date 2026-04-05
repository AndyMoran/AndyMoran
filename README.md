# Andy Moran — Quantitative Researcher

My MPlan research at Manchester used Cuba's post-Soviet subsidy collapse— specifically modelling how Manchester's food system would respond to a comparable climate-driven shock, and what that implies for UK policy under energy crisis conditions. The research was interesting; the frustration was that its prescriptions couldn't be measured. I couldn't reconcile 'top-down' technocratic theory with ground-level reality. Rather than continue 'hallucinating' policies, I left the field to build things that had to work in the real world.

But my planning research remains relevant: Cuba is again experiencing severe energy constraints, and the system‑level responses echo the same dynamics I studied years ago. Those patterns appear today in the geopolitical volatility of the Strait of Hormuz, and this reinforced a core truth: uncertainty has a structural pattern that intuition alone cannot capture. Reading Annie Duke’s Thinking in Bets provided the necessary pivot: a move toward the formal probabilistic tools needed to reason honestly about real‑world risk.

I've now worked through the frequentist foundations and moved into Bayesian modelling. I've built projects that moved from "this seems straightforward" to "this is a lot more complicated than I thought" to "this model doesn't fit the data". I've iterated, failed, and actively invited criticism, because I want to get things right. 

My last completed project, "Detecting False Signals in Mean-Reversion Models", used Premier League xG data as a case study. It started as a search for signal and ended as a lesson in how easily rolling means create artefacts. It didn't prove what I hoped. Instead, it provided a clear demonstration of how smoothing can create spurious signals that pass every standard test. I abandoned the signal because I care about ground truth, quick empirical feedback, and models that survive contact with data, not just persuade in slide decks. If the data disagrees with the model, the data wins. I’m interested in predictive power, not models that protect an expert’s reputation.

I'm now applying Bayesian modelling, regime-switching processes, causal inference, and structured null testing to GB electricity markets. The specific question: has the evening demand ramp already begun to change shape as EV adoption grows, and what is that structural shift worth to a storage asset before the forward curve prices it in?


# Current Focus

I’m building a curated, professional portfolio that reflects both my formal training and my independent analytical interests. My work emphasises:

- clean, readable analysis

- principled statistical reasoning

- reproducible workflows

- uncertainty‑aware modelling

- clear narrative structure

- decision‑ready insights

I’m now extending these skills into energy‑sector forecasting, risk modelling, and probabilistic optimisation.

# Featured Projects

## Ahead of the Curve — Structural Change in GB Diurnal Price Shape

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

**Techniques:** Bayesian modelling, posterior predictive simulation, null‑model construction

**Focus:** Detecting when rolling‑mean “signals” are artefacts rather than genuine effects.

**Repo:** https://github.com/AndyMoran/xg-spread-model

This project started as a search for signal and ended as a sober lesson. The result a Bayesian failure‑mode analysis showing how rolling‑mean spreads in football xG data can produce convincing‑looking patterns even when no real effect exists. The model builds a principled null distribution, simulates thousands of fake seasons, and compares the observed statistic against that null to quantify whether the pattern is real or an artefact of autocorrelation and variance instability.

Demonstrates:

- principled null‑model construction

- posterior predictive simulation for false‑positive detection

- diagnosing artefacts in rolling‑window time‑series models

- clear communication of uncertainty and model limitations


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

# Connect

Building toward energy trading and storage dispatch analytics.
Available for coffee — particularly interested in talking
to people working on storage optimisation, flexibility markets,
and DER price impact. Feel free to explore the repositories
or reach out directly.
andrewgmoran@gmail.com
