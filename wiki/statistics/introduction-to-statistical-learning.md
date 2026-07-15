---
type: Reference
title: "An Introduction to Statistical Learning (ISL)"
tags: [statistics, statistical-learning, machine-learning, regression, classification, textbook]
timestamp: 2026-07-14
source: https://www.statlearning.com/
---

# An Introduction to Statistical Learning (ISL)

*An Introduction to Statistical Learning* by Gareth James, Daniela Witten, Trevor Hastie,
and Robert Tibshirani (Springer; freely available at statlearning.com, now in editions with
both R and Python labs) is the accessible on-ramp to the field of
[statistical learning](statistical-learning.md). It is the deliberately gentler companion to
the same authors' more mathematical [*Elements of Statistical Learning*](../ai/elements-of-statistical-learning.md)
(ESL): ISL covers much of the same territory but replaces heavy theory with intuition,
worked examples, and hands-on programming labs, so that a reader with only basic statistics
and no measure theory can start building and evaluating predictive models.

## Scope and approach

The book is organized around methods and the ideas needed to use them well.

- **Framing.** It opens by distinguishing supervised from unsupervised learning, prediction
  from inference, and — crucially — introduces the **bias–variance trade-off** and the gap
  between training and test error. This assessing-model-accuracy theme runs through every
  later chapter and is the conceptual core of
  [statistical-learning.md](statistical-learning.md).
- **Linear and logistic models.** Simple and multiple linear [regression](regression.md),
  then classification via logistic regression and linear/quadratic discriminant analysis and
  naive Bayes. These establish the interpretable baseline against which flexible methods are
  judged.
- **Resampling.** Cross-validation and the bootstrap, presented as the practical tools for
  estimating test error and uncertainty without extra data — the applied face of
  [resampling-and-monte-carlo.md](resampling-and-monte-carlo.md).
- **Model selection and regularization.** Subset selection, ridge regression, and the lasso,
  motivating why shrinking or zeroing coefficients improves prediction — the same
  penalization ideas that pervade [../ai/machine-learning.md](../ai/machine-learning.md).
- **Beyond linearity.** Polynomial regression, splines, and generalized additive models.
- **Tree-based methods.** Decision trees, bagging, random forests, and boosting.
- **Support vector machines** and, in the later editions, **deep learning** as a chapter of
  its own, plus **survival analysis**, **unsupervised learning** (principal components
  analysis and clustering), and **multiple testing**.

Every chapter closes with lab code and exercises, so the reader implements each method on
real datasets rather than only reading about it.

## Audience and role

ISL is written for advanced undergraduates, master's students, and practitioners in any
quantitative field who want to *apply* statistical learning without first mastering its
theory. It teaches judgment — when a flexible method helps, why regularization guards against
overfitting, how to estimate honest test error — and leaves the proofs to ESL. In a learning
path it sits before [*The Elements of Statistical Learning*](../ai/elements-of-statistical-learning.md):
read ISL to build working intuition and skills, then move to ESL for the underlying theory.
It connects backward to inference foundations in [estimation.md](estimation.md) and forward
to the broader machine-learning treatment in [../ai/machine-learning.md](../ai/machine-learning.md).

## References

- [An Introduction to Statistical Learning — official site (statlearning.com)](https://www.statlearning.com/)
