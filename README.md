# Andy Moran — Quantitative Researcher

I’ve long been interested decisions made under uncertainty. Annie Duke’s Thinking in Bets was an early influence, and it pushed me toward a more formal path: data analytics, data science, and the maths needed to understand models properly. I’ve worked through the frequentist foundations and moved into Bayesian modelling. I've built projects that feel like “this seems straightforward” to “this is a lot more complicated than I thought.” I've iterated and failed and implemented adversarial reviews happily, because I want to get thing right.

My latest project, "Detecting False Signals in Mean-Reversion Models", used Premier League xG data as a case study. It started as a search for signal and ended as a lesson in how easily rolling means create artefacts. It didn’t prove what I hoped. Instead, it provided a clear demonstration of how smoothing can create spurious signals that pass every standard test. It did prove something more useful: where the methodology breaks
and why.

So, I’m interested in how systems fail — not in theory, but in the way real things break when assumptions give out. I care about the ground truth, fast feedback loops, and models that don’t hide behind a slide deck. If the world disagrees with the model, the world wins. Honesty appeals to me even if it disappoints.

I’m not drawn to performative work. As David Graeber put it, some jobs exist to look busy rather than to understand anything. I prefer environments where the ground truth matters, the uncertainty matters, and the model has to earn its keep.

I lean toward Bayesian modelling, regime‑switching processes, and causal inference — tools that make uncertainty explicit rather than pretending it isn’t there.

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

A Bayesian failure‑mode analysis showing how rolling‑mean spreads in football xG data can produce convincing‑looking patterns even when no real effect exists. The model builds a principled null distribution, simulates thousands of fake seasons, and compares the observed statistic against that null to quantify whether the pattern is real or an artefact of autocorrelation and variance instability.

Demonstrates:

principled null‑model construction

posterior predictive simulation for false‑positive detection

diagnosing artefacts in rolling‑window time‑series models

clear communication of uncertainty and model limitations

## VAR and Premier League Home Advantage: A Bayesian AnalysisTechniques: Bayesian modelling, sensitivity analysis, segmentation, causal reasoning

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

- Building messy‑data projects using probabilistic forests and market‑maker models

- Expanding into energy‑sector forecasting and risk modelling

# Connect

Open to conversations about data, modelling, or interesting analytical problems.
Feel free to explore my repos or reach out.
