# Andy Moran — Quantitative Researcher

My background is in policy analysis under uncertainty. My MPlan research at Manchester used Cuba's post-Soviet subsidy collapse as a structural transfer model — specifically modelling how Manchester's food system would respond to a comparable climate-driven shock, and what that implies for UK policy under energy crisis conditions. The research was interesting. The frustration was that its prescriptions couldn't be measured. Reading Annie Duke's Thinking in Bets and her probabilistic approach to decision-making pushed me toward a more formal path: data analytics, data science, and the maths needed to understand models properly.

I've now worked through the frequentist foundations and moved into Bayesian modelling. I've built projects that feel like "this seems straightforward" to "this is a lot more complicated than I thought." I've iterated, failed, and actively invited criticism, because I want to get things right.

My last completed project, "Detecting False Signals in Mean-Reversion Models", used Premier League xG data as a case study. It started as a search for signal and ended as a lesson in how easily rolling means create artefacts. It didn't prove what I hoped. Instead, it provided a clear demonstration of how smoothing can create spurious signals that pass every standard test. I abandoned the signal because I care most about the ground truth, value fast feedback loops, and models that don't hide behind a slide deck. If the world disagrees with the model, the world wins. Honesty appeals to me even if it disappoints. Performative work appeals even less.

I'm currently applying Bayesian modelling, regime-switching processes, causal inference, and structured null testing to GB electricity markets. The specific question: has the evening demand ramp already begun to change shape as EV adoption grows, and what is that structural shift worth to a storage asset before the forward curve prices it in?


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

## xG Spread Failure Model — Null‑Model Calibration & False‑Signal Detection

Techniques: Bayesian modelling, posterior predictive simulation, null‑model construction
Focus: Detecting when rolling‑mean “signals” are artefacts rather than genuine effects
Repo: https://github.com/AndyMoran/xg-spread-model

This project started as a search for signal and ended as a sober lesson. The result a Bayesian failure‑mode analysis showing how rolling‑mean spreads in football xG data can produce convincing‑looking patterns even when no real effect exists. The model builds a principled null distribution, simulates thousands of fake seasons, and compares the observed statistic against that null to quantify whether the pattern is real or an artefact of autocorrelation and variance instability.

Demonstrates:

principled null‑model construction

posterior predictive simulation for false‑positive detection

diagnosing artefacts in rolling‑window time‑series models

clear communication of uncertainty and model limitations


## Ahead of the Curve — Structural Change in GB Diurnal Price Shape

EV smart charging and storage dispatch optimisationregime detection diurnal harmonic analysis battery dispatch causal inference

[→ Repository] (in progress)

GB evening demand shape is changing as EV adoption grows and smart charging mandates take effect. The question for a storage asset is not whether the shape is changing — it is — but when the change becomes large enough to materially affect the battery arbitrage spread, and what that shift is worth in NPV terms.

This project builds a detection framework for structural change in the GB evening ramp using Elexon half-hourly settlement data, DVLA EV registration data, and OZEV chargepoint installation data. The identification strategy uses the smart charging mandate as a quasi-experimental treatment — its implementation date is unambiguous in a way that gradual adoption curves are not.

The commercial deliverable is an option value calculation: the NPV difference between a 2MW battery asset operating in a pre-ramp-flattening price regime versus a post-flattening one, reported by adoption scenario and gas price scenario. This is the number a storage investor needs before the market prices the shift in.

The diagnostic framework from the xG project carries over directly. The four-step null testing sequence runs on GB settlement data before any signal pipeline is built.
Currently in active development. Notebooks and interim results added as completed.

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

Techniques: Monte Carlo simulation, Bayesian decision‑making, scenario analysis
Focus: Pricing strategy under uncertainty
Repo: https://github.com/AndyMoran/Cyclistic_bayesian_analysis

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

Techniques: Gamma likelihood, Fourier circadian modelling, hierarchical structure
Focus: Behavioural segmentation & personalised engagement
Repo: https://github.com/AndyMoran/bellabeat_bayesian_analysis

A hierarchical Gamma/Fourier model capturing 24‑hour activity rhythms across Bellabeat personas. Includes model comparison (WAIC/LOO), full diagnostics, and literature integration on circadian modelling. Uses probability‑of‑superiority to compare personas hour‑by‑hour.

Demonstrates:

- modelling cyclic behaviour with Fourier series

- principled handling of right‑skewed data

- uncertainty‑aware behavioural comparison

# Learning Portfolio (Completed Courses)

Techniques: Data cleaning, wrangling, visualisation, structured reporting
Focus: Foundations & breadth
Repo: https://github.com/AndyMoran/learning-portfolio

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

- Expanding into energy‑sector forecasting and risk modelling

# Connect

Building toward energy trading and storage dispatch analytics.
Available for coffee — particularly interested in talking
to people working on storage optimisation, flexibility markets,
and DER price impact. Feel free to explore the repositories
or reach out directly.
andrewgmoran@gmail.com
