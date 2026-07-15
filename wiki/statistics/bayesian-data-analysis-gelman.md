---
type: Reference
title: "Bayesian Data Analysis (BDA3)"
tags: [statistics, bayesian, inference, mcmc, monte-carlo, workflow, textbook, gelman]
timestamp: 2026-07-14
source: http://www.stat.columbia.edu/~gelman/book/
---

# Bayesian Data Analysis (BDA3)

*Bayesian Data Analysis*, third edition (Gelman, Carlin, Stern, Dunson, Vehtari, and Rubin;
CRC Press, 2013 — commonly "BDA3"), is the reference text for applied Bayesian statistics.
Its distinctive stance is that Bayesian inference is not merely a philosophy of probability
but a **practical workflow** for building, fitting, checking, and improving models on real
data. It develops the theory of [Bayesian inference](bayesian-inference.md) in enough depth
to be rigorous, but its center of gravity is applied: how to specify priors and likelihoods
for genuine problems, how to compute the posterior when it has no closed form, and how to
tell whether the resulting model is any good.

## Scope and structure

The book proceeds in five broad parts.

**Fundamentals of Bayesian inference.** It starts from Bayes' theorem — posterior ∝
likelihood × prior — and works through single-parameter models, the role of conjugate and
noninformative priors, multiparameter models (including the normal model with unknown mean
and variance), and large-sample / asymptotic normality results that connect Bayesian
estimates to their frequentist counterparts. This anchors [bayesian-inference.md](bayesian-inference.md).

**Fundamentals of Bayesian data analysis.** Here the workflow emerges: hierarchical
(multilevel) models that partially pool information across groups, **model checking** via
posterior predictive checks, comparison and expansion of models, and the design of studies
and treatment of missing data. The emphasis on posterior predictive checking — simulating
replicated data from the fitted model and comparing it to what was observed — is one of the
book's most influential contributions.

**Advanced computation.** Because realistic posteriors are almost never analytic, a large
section is devoted to computation: the general logic of Monte Carlo approximation, Markov
chain Monte Carlo (Metropolis–Hastings and Gibbs sampling), Hamiltonian Monte Carlo and the
No-U-Turn Sampler behind modern tools like Stan, convergence diagnostics, and modal/variational
approximations. This is the practical face of
[resampling-and-monte-carlo.md](resampling-and-monte-carlo.md): sampling *from* a posterior
to estimate any quantity of interest.

**Regression models.** The book then builds Bayesian versions of the standard applied
toolkit — linear and generalized linear [regression](regression.md), hierarchical
regression, and robust and nonparametric extensions — treating regression as a special case
of the general model-building workflow rather than a separate subject.

**Nonparametric and advanced models.** Closing chapters cover Gaussian processes, Dirichlet
processes and other nonparametric priors, and mixture and decision-theoretic models.

## Approach and audience

BDA3 is aimed at graduate students and practitioners who will actually fit models. Its
recurring loop — propose a model, fit it, check it against the data, and expand it where it
fails — has shaped how a generation of applied statisticians work, and it maps cleanly onto
the iterate-and-validate mindset of applied machine learning
([../ai/machine-learning.md](../ai/machine-learning.md)). It pairs naturally with a
theory-first text like [Casella & Berger](casella-berger-statistical-inference.md) for
foundations and with [estimation.md](estimation.md) and
[hypothesis-testing.md](hypothesis-testing.md) as the frequentist counterpoints to the
Bayesian treatment it develops.

## References

- [Bayesian Data Analysis — authors' book page (Andrew Gelman, Columbia)](http://www.stat.columbia.edu/~gelman/book/)
