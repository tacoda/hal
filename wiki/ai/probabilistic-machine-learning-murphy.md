---
type: Reference
title: "Probabilistic Machine Learning (Murphy)"
tags: [machine-learning, probability, bayesian, generative-models, deep-learning, statistics]
timestamp: 2026-07-14
source: https://probml.github.io/pml-book/
---

# Probabilistic Machine Learning (Murphy)

Kevin P. Murphy's *Probabilistic Machine Learning* is a two-volume book series (MIT
Press) that presents the whole of modern [machine learning](machine-learning.md) through
a single unifying lens: **probability**. It is the successor to his widely used 2012
text *Machine Learning: A Probabilistic Perspective*, rewritten and split into
*Book 1: An Introduction* (2022) and *Book 2: Advanced Topics* (2023). The organizing
claim is that almost every ML method — linear models, deep nets, clustering, generative
models — can be understood as **probabilistic inference**: positing a model with
uncertain parameters, then reasoning about those parameters and about predictions using
the rules of probability.

## The probabilistic/Bayesian lens

The book grounds everything in [probability and statistics](../statistics/index.md).
Two ideas recur throughout:

- **Maximum likelihood (and MAP) estimation** — pick parameters $\theta$ that make the
  observed data most probable, $\hat\theta = \arg\max_\theta p(\mathcal{D} \mid \theta)$.
  This reframes familiar losses: squared error *is* the negative log-likelihood of a
  Gaussian; cross-entropy *is* the negative log-likelihood of a categorical. So
  "minimizing loss" and "maximizing likelihood" are the same act.
- **Bayesian inference** — treat $\theta$ itself as a random variable with a **prior**
  $p(\theta)$, and update to a **posterior** $p(\theta \mid \mathcal{D}) \propto
  p(\mathcal{D} \mid \theta)\,p(\theta)$ via Bayes' rule. Predictions marginalize over
  the posterior, which propagates *uncertainty* into the answer rather than committing
  to a single point estimate — central to decision-making under uncertainty.

## What the volumes cover

**Book 1 (Introduction)** builds the foundations and the mainstream supervised/
unsupervised toolkit:

- Probability, statistics, and the [linear algebra](../math/index.md) and optimization
  prerequisites.
- **Linear models** — linear and logistic regression as probabilistic models
  ([supervised learning](supervised-learning.md)).
- **Deep neural networks** — feedforward, convolutional, recurrent, and
  attention/[transformer](transformers-and-attention.md) architectures, trained by
  [gradient descent](backpropagation-and-gradient-descent.md), viewed as flexible
  conditional distributions $p(y \mid x)$ — see [deep learning](deep-learning.md).
- **Unsupervised learning** — clustering, dimensionality reduction, and latent-variable
  models ([unsupervised learning](unsupervised-learning.md)).

**Book 2 (Advanced Topics)** goes deeper into inference machinery and modeling:

- Exact and approximate **inference** — variational inference, Markov chain Monte Carlo
  (MCMC), and the sampling methods that make Bayesian models tractable.
- **Generative models** — variational autoencoders, normalizing flows, diffusion models,
  and autoregressive models: the probabilistic account of
  [generative models](generative-models.md).
- Graphical models, Gaussian processes, and structured prediction.

## The predict-then-decide pipeline

```mermaid
flowchart LR
    P[Prior p θ] --> B[Bayes' rule]
    D[Data 𝒟] --> B
    B --> Post[Posterior p θ | 𝒟]
    Post --> Pred[Predictive p y | x, 𝒟]
    Pred --> Dec[Decision under uncertainty]
```

## Why it matters

Framing ML probabilistically is not merely aesthetic. It gives a *principled* account of
where loss functions come from (likelihoods), how to combine prior knowledge with data
(priors), and how to represent what the model *doesn't* know (posterior uncertainty) —
which is exactly what safety-critical and high-stakes systems need. It also unifies
methods that look unrelated: a classifier, a clustering algorithm, and a
[generative model](generative-models.md) are all inference in a probabilistic model,
differing only in structure. Murphy is the standard modern reference for anyone who wants
the field's coherent mathematical core, drawing on
[statistics](../statistics/index.md) and [mathematics](../math/index.md).

## References

- [Probabilistic Machine Learning — Kevin Murphy (book series homepage)](https://probml.github.io/pml-book/)
  — free draft PDFs of both volumes.
