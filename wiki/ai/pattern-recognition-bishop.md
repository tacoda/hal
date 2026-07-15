---
type: Reference
title: "Pattern Recognition and Machine Learning"
tags: [machine-learning, bayesian, probabilistic-models, graphical-models, kernels, em, sampling, textbook]
timestamp: 2026-07-14
source: https://www.microsoft.com/en-us/research/publication/pattern-recognition-machine-learning/
---

# Pattern Recognition and Machine Learning

*Christopher M. Bishop — Springer, 2006.* Known everywhere as **PRML**, this is the
classic graduate text for machine learning taught from a thoroughly **Bayesian**
viewpoint. Its 738 pages assume no prior ML knowledge but do assume comfort with
multivariate calculus and linear algebra, and it was the first mainstream textbook to
give unified, comprehensive coverage of probabilistic graphical models and deterministic
approximate-inference methods. The distinguishing thread is a consistent probabilistic
stance: models express distributions, learning is inference over parameters, and
predictions integrate over uncertainty rather than committing to a single point estimate.

## The probabilistic spine

Bishop opens with probability theory, decision theory, and information theory as the
common language, then repeatedly contrasts two ways of using it: the **frequentist /
maximum-likelihood** recipe (fit a point estimate) and the **Bayesian** recipe (maintain
a posterior distribution and marginalize). This framing is what makes the book cohere —
regularization becomes a prior, model selection becomes marginal likelihood, and
overfitting is understood as failing to account for parameter uncertainty. It directly
grounds [machine-learning](machine-learning.md) and
[generalization-and-regularization](generalization-and-regularization.md).

## Arc of topics

- **Linear models** for regression and classification — least squares, the bias–variance
  decomposition, logistic regression, and their Bayesian treatments. See
  [supervised-learning](supervised-learning.md).
- **Neural networks** — the multilayer perceptron and error backpropagation, presented as
  flexible nonlinear basis-function models.
- **Kernel methods** — dual representations, Gaussian processes, and support vector
  machines, showing how fixed basis functions can be replaced by kernels.
- **Graphical models** — directed (Bayesian) and undirected (Markov random field)
  networks, and inference by message passing / the sum-product algorithm — the book's
  signature contribution to teaching.
- **Latent-variable models and the EM algorithm** — mixture models, k-means, and
  Expectation–Maximization as the engine for learning with hidden variables. See
  [unsupervised-learning](unsupervised-learning.md).
- **Approximate inference** — variational (deterministic) methods and **sampling**
  (MCMC) for posteriors that have no closed form.
- **Continuous latent variables** (PCA, probabilistic PCA), **sequential data** (HMMs,
  linear dynamical systems), and **combining models** (boosting, mixtures of experts).

## Why it endures

PRML remains the reference for anyone who wants to understand ML as principled
probabilistic modeling rather than a bag of algorithms. Its treatment of graphical
models, EM, and variational inference is still among the clearest available, and the
Bayesian perspective it champions underlies much of modern probabilistic machine
learning. It pairs naturally with the more frequentist, statistics-flavored
[The Elements of Statistical Learning](elements-of-statistical-learning.md).

## Related notes

- Concepts it anchors: [machine-learning](machine-learning.md),
  [supervised-learning](supervised-learning.md),
  [unsupervised-learning](unsupervised-learning.md),
  [generalization-and-regularization](generalization-and-regularization.md),
  [neural-networks](neural-networks.md).
- The probabilistic core connects to [statistics](../statistics/index.md) and
  [mathematics](../math/index.md).

## References

- [Pattern Recognition and Machine Learning — Microsoft Research (free PDF)](https://www.microsoft.com/en-us/research/publication/pattern-recognition-machine-learning/)
