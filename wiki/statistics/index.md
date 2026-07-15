---
type: Index
title: Statistics
tags: [statistics, probability, inference, index]
timestamp: 2026-07-14
---

# Statistics

Reasoning under uncertainty — from the axioms of probability up to causal inference and
the statistical view of machine learning. This folder is the college-level core, and it is
the field [artificial intelligence](../ai/index.md) draws on most after
[mathematics](../math/index.md): every loss, estimator, and evaluation in ML is a
statistical object.

## The shape of the field

It starts with [probability](probability.md) — the calculus of uncertainty — then
[random variables and distributions](random-variables-and-distributions.md) and their
[expectations and moments](expectation-and-moments.md) (where the Law of Large Numbers and
the Central Limit Theorem live). [Descriptive statistics](descriptive-statistics.md)
summarizes data; **inference** generalizes from it, along two traditions:
[estimation](estimation.md) + [hypothesis testing](hypothesis-testing.md) (frequentist)
and [Bayesian inference](bayesian-inference.md). [Regression](regression.md) models
relationships; [resampling and Monte Carlo](resampling-and-monte-carlo.md) replaces
closed-form math with computation; [experimental design & A/B testing](experimental-design-and-ab-testing.md)
and [causal inference](causal-inference.md) get at *causation*, not just correlation.
[Statistical learning](statistical-learning.md) is the bridge to
[machine learning](../ai/machine-learning.md).

## Concepts

- [Probability](probability.md) — sample spaces, axioms, conditional probability, Bayes' theorem, frequentist vs Bayesian meaning
- [Random Variables and Distributions](random-variables-and-distributions.md) — pmf/pdf/cdf, the key named distributions, joint/marginal/conditional
- [Expectation and Moments](expectation-and-moments.md) — mean, variance, covariance, and the LLN/CLT that make averaging and the normal universal
- [Descriptive Statistics](descriptive-statistics.md) — center, spread, shape, quantiles, robustness; describing a sample vs inferring a population
- [Estimation](estimation.md) — MLE, method of moments, bias/variance, consistency, standard errors, confidence intervals
- [Hypothesis Testing](hypothesis-testing.md) — null/alternative, p-values, Type I/II errors and power, t/χ²/ANOVA, the replication-crisis critique
- [Bayesian Inference](bayesian-inference.md) — priors, likelihoods, posteriors; conjugacy, credible intervals, MCMC, prior sensitivity
- [Regression](regression.md) — OLS and its assumptions, logistic regression and GLMs, ridge/lasso, diagnostics
- [Resampling and Monte Carlo](resampling-and-monte-carlo.md) — bootstrap, cross-validation, permutation tests, MCMC
- [Experimental Design and A/B Testing](experimental-design-and-ab-testing.md) — randomization, treatment/control, power, blocking, the peeking trap
- [Causal Inference](causal-inference.md) — potential outcomes, DAGs and do-calculus, IV and difference-in-differences
- [Statistical Learning](statistical-learning.md) — the statistics/ML bridge: supervised vs unsupervised, bias-variance, train/test error, model selection

## Canonical works

- [All of Statistics](all-of-statistics-wasserman.md) — Larry Wasserman; the fast rigorous survey for CS/ML readers
- [Statistical Inference](casella-berger-statistical-inference.md) — Casella & Berger; the graduate mathematical-statistics standard
- [Bayesian Data Analysis](bayesian-data-analysis-gelman.md) — Gelman et al. (BDA3); the applied Bayesian workflow
- [An Introduction to Statistical Learning](introduction-to-statistical-learning.md) — James, Witten, Hastie, Tibshirani; the accessible on-ramp to ESL
- [The Book of Why](the-book-of-why-pearl.md) — Pearl & Mackenzie; the ladder of causation, DAGs, do-calculus

## Related fields

[Mathematics](../math/index.md) (probability's foundations, information theory),
[artificial intelligence](../ai/index.md) (statistical learning), [economics](../economics/index.md)
(econometrics — pending), and the evaluation practice in
[AI Platform](../ai-platform/index.md) (evals, A/B testing).
