---
type: Reference
title: "All of Statistics: A Concise Course in Statistical Inference"
tags: [statistics, inference, probability, machine-learning, textbook, wasserman]
timestamp: 2026-07-14
source: https://www.stat.cmu.edu/~larry/all-of-statistics/
---

# All of Statistics: A Concise Course in Statistical Inference

Larry Wasserman's *All of Statistics* (Springer, 2004) is a fast, rigorous, single-volume
survey of modern statistical inference written explicitly for people coming from computer
science, machine learning, and related quantitative fields rather than from a traditional
statistics program. Its stated ambition is compression: to cover in one book the material
that is usually spread across a probability course, a theory-of-statistics course, and
several applied courses, so that a mathematically literate reader can get to the working
core of the subject quickly. The trade-off is deliberate — proofs are sketched or cited
rather than belabored, and breadth is chosen over the exhaustive depth of a dedicated
graduate text like [Casella & Berger](casella-berger-statistical-inference.md).

## Scope and structure

The book moves in three arcs. The **first** is a self-contained treatment of probability:
sample spaces, random variables and their distributions, expectation and variance, the key
inequalities (Markov, Chebyshev, Hoeffding), and the limit theorems — convergence in
probability and distribution, the law of large numbers, and the central limit theorem. This
material anchors [probability.md](probability.md).

The **second** arc is statistical inference proper. Wasserman organizes it around three
questions: how to estimate a quantity, how to construct a confidence set for it, and how to
test a hypothesis about it. He develops the empirical distribution function and statistical
functionals, the bootstrap, parametric point estimation via maximum likelihood and the
method of moments, the properties that make an estimator good (consistency, bias, variance,
asymptotic normality, efficiency), and interval estimation — the substance of
[estimation.md](estimation.md). Hypothesis testing gets both the Wald, likelihood-ratio,
and permutation machinery and a frank discussion of p-values and multiple testing, feeding
[hypothesis-testing.md](hypothesis-testing.md). A compact chapter presents
[Bayesian inference](bayesian-inference.md) side by side with the frequentist view, so the
reader sees where the two agree and where they diverge.

The **third** arc turns toward data-analysis and learning methods: [regression.md](regression.md)
(linear and logistic, and the general linear model), multivariate models and graphical
models, directed acyclic graphs and a first look at [causal inference](causal-inference.md),
density estimation and nonparametric smoothing, classification, and an introduction to
[statistical learning](statistical-learning.md) theory including VC dimension. This is the
part that makes the book a natural bridge to
[../ai/machine-learning.md](../ai/machine-learning.md): it frames prediction and
classification as inference problems and connects the bias–variance trade-off to model
complexity, the same theme developed at length in
[../ai/elements-of-statistical-learning.md](../ai/elements-of-statistical-learning.md).

## Approach and audience

The distinctive feature is pace and framing. Wasserman assumes calculus and linear algebra,
introduces measure-theoretic ideas only where they earn their keep, and consistently
motivates each tool by the inference question it answers rather than by mathematical
lineage. Because it names the machine-learning connections directly — the empirical risk it
minimizes, the estimators it fits, the guarantees it can and cannot claim — it has become a
common "statistics for ML" reference. It works well as a rapid first pass or a review, with
denser texts consulted when a particular result needs full rigor.

## References

- [All of Statistics — author's book page (Larry Wasserman, CMU)](https://www.stat.cmu.edu/~larry/all-of-statistics/)
