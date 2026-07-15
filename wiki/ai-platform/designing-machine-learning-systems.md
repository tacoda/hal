---
type: Reference
title: Designing Machine Learning Systems
tags: [ml-systems, mlops, production, monitoring, data-engineering, reliability]
timestamp: 2026-07-14
source: https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/
---

# Designing Machine Learning Systems

Chip Huyen's 2022 book treats machine learning as a *systems* problem, not a modeling
problem. The insight that organizes the whole book: in production, the model is a small
fraction of the work. What determines whether an ML product succeeds is everything around
the model — the data pipelines, the deployment path, the monitoring, and the feedback loop
that keeps the system useful as the world changes. Research ML optimizes a fixed benchmark;
production ML operates inside a live business with shifting data, latency budgets,
stakeholders, and consequences for being wrong.

## The reframe: research ML vs. production ML

Huyen draws a sharp line between the two settings. Research chases a single metric on a
static dataset. Production has to satisfy *many* objectives at once — accuracy, latency,
cost, fairness, interpretability — that trade off against each other, and it does so against
data that is never static. A model that is state-of-the-art on a leaderboard can be the wrong
choice in production because it is too slow, too expensive to serve, or too brittle when the
input distribution drifts.

## An iterative process, not a pipeline

She frames building an ML system as a loop rather than a linear pipeline: frame the problem
against a business objective, engineer the data, train and evaluate, deploy, monitor, and use
what monitoring tells you to reframe and start again. The reliability, scalability,
maintainability, and adaptability requirements she names for ML systems echo classic software
systems thinking — this is where the book overlaps with
[Designing Data-Intensive Applications](../distributed-systems/designing-data-intensive-applications.md) and the
operational concerns of [Production-Ready Microservices](../software-architecture/production-ready-microservices.md).

```mermaid
flowchart LR
    A[Frame problem<br/>vs business objective] --> B[Data engineering]
    B --> C[Feature engineering]
    C --> D[Train & evaluate]
    D --> E[Deploy]
    E --> F[Monitor]
    F -->|drift, degradation,<br/>feedback| A
```

## Data is the leverage point

A large share of the book is about data, because that is where most production ML value and
most production ML pain live. Huyen covers data sources and formats, the tradeoffs between
row-major and column-major storage, structured vs. unstructured data, the modes of dataflow
(through databases, through services, through real-time transport), and batch vs. stream
processing. Then: sampling, labeling, handling class imbalance, feature engineering, and the
data leakage traps that quietly inflate offline metrics and then collapse in production.

## The part everyone underestimates: monitoring and drift

The failure mode that defines production ML is **data distribution shift** — the world the
model was trained on stops matching the world it is serving. Performance decays silently
because nothing errors out; the predictions just get worse. Huyen argues monitoring is not a
nice-to-have bolted on at the end but a first-class design requirement: you instrument the
system to detect covariate, label, and concept shift, and you build the feedback loop that
triggers retraining. This is the ML-specific analog of the operational monitoring in
[agent observability](agent-observability.md) — you cannot manage what you cannot see, and ML
systems degrade in ways ordinary software does not.

## Continual learning and the test-in-production stance

Because the data keeps moving, the system has to keep learning. Huyen makes the case for
continual learning and for evaluating in production (shadow deployments, canary releases,
A/B tests, contextual bandits) rather than trusting a frozen offline number. Deployment is a
spectrum of strategies for limiting blast radius while learning from real traffic — the same
graceful-degradation instinct that resilience engineering formalizes.

## Why it still matters in the foundation-model era

DMLS predates the LLM-application wave, and Huyen's own follow-up
[AI Engineering](ai-engineering-huyen.md) extends this systems lens to foundation models. But
the core discipline transfers directly: data quality dominates, monitoring is non-negotiable,
distribution shift is the enemy, and the model is the easy part. It remains a staple of the
[AI engineering bookshelf](../misc/ai-engineering-bookshelf.md) and pairs naturally with the
production-first attitude in the [common-sense guide to AI engineering](common-sense-guide-to-ai-engineering.md).

## References

- [Designing Machine Learning Systems — O'Reilly](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/)
- [Chip Huyen's MLOps guide (companion material)](https://huyenchip.com/mlops/)
