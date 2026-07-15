---
type: Reference
title: "Introductory Econometrics: A Modern Approach"
tags: [economics, econometrics, regression, ols, causal-inference, textbook]
timestamp: 2026-07-14
source: https://www.cengage.com/c/introductory-econometrics-a-modern-approach-7e-wooldridge/9781337558860/
---

# Introductory Econometrics: A Modern Approach

Jeffrey Wooldridge's *Introductory Econometrics: A Modern Approach* is the standard
undergraduate [econometrics](econometrics.md) text — the book that teaches economists how
to take the theory of [supply and demand](supply-and-demand.md) and behavior to real data
and estimate the relationships it predicts. Wooldridge, a Michigan State econometrician and
Fellow of the Econometric Society, first published it in the mid-1990s; it is now the most
widely assigned econometrics text at the undergraduate level.

## The "modern approach"

The book's framing choice — and its title — is to organize everything around the goal of
estimating *ceteris paribus* (all-else-equal) effects from observational data, rather than
presenting econometrics as a sequence of matrix formulas. Assumptions are stated as
conditions on the population and the sampling, and every result is judged by whether it
supports a credible causal or predictive claim. This puts identification and interpretation
ahead of mechanical derivation.

## Scope

- **The linear regression model.** The core of the book is ordinary least squares (OLS):
  simple and multiple [regression](../statistics/regression.md), the interpretation of
  coefficients, goodness of fit, and the Gauss–Markov assumptions under which OLS is the
  best linear unbiased estimator. See [regression](../statistics/regression.md) for the
  underlying statistical machinery.
- **Inference and diagnostics.** Hypothesis testing, confidence intervals, functional form
  (logs, quadratics, interactions), dummy variables, and what goes wrong under
  heteroskedasticity and other violations — with robust standard errors as the fix.
- **Cross section, time series, and panels.** The book is structured by data type: it moves
  from cross-sectional data to time-series regression (trends, seasonality,
  autocorrelation) to panel-data methods (fixed effects, first differencing) that exploit
  repeated observations to control for unobserved heterogeneity.
- **Beyond OLS.** Instrumental variables and two-stage least squares for endogeneity,
  simultaneous-equations models, and limited-dependent-variable models (logit, probit,
  Tobit) for binary and censored outcomes.

## Why it matters

Wooldridge's emphasis on assumptions-you-can-defend and ceteris-paribus interpretation is
what makes the book a bridge from statistics to empirical economics: it teaches not just
how to compute an estimate but when that estimate answers the question you asked. The
companion graduate text, *Econometric Analysis of Cross Section and Panel Data*, extends
the same program to the research frontier.

## References

- [Introductory Econometrics: A Modern Approach, 7th ed. — Cengage](https://www.cengage.com/c/introductory-econometrics-a-modern-approach-7e-wooldridge/9781337558860/)
