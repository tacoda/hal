---
type: Reference
title: "Statistical Inference (Casella & Berger)"
tags: [statistics, inference, mathematical-statistics, estimation, hypothesis-testing, textbook]
timestamp: 2026-07-14
source: https://www.cengage.com/c/statistical-inference-2e-casella-berger/9780534243128/
---

# Statistical Inference (Casella & Berger)

George Casella and Roger L. Berger's *Statistical Inference* (2nd edition, Duxbury/Cengage,
2002) is the standard graduate text for mathematical statistics in North American programs.
Where [Wasserman's *All of Statistics*](all-of-statistics-wasserman.md) sprints through the
subject for a broad quantitative audience, Casella & Berger is the deliberate, proof-first
treatment: it builds the theory of inference from the probability foundations upward and
expects the reader to work through the derivations. It is the book a statistics PhD student
is likely to be examined on, and the reference practitioners return to when they need the
precise conditions behind a result.

## Scope and structure

The book is built in two movements. The **first half constructs the probabilistic
machinery** that inference stands on. It develops probability theory, single random
variables and their transformations, expectation and moment generating functions, families
of common distributions, and then multiple random variables — joint and conditional
distributions, covariance and correlation, hierarchical and mixture models. A pivotal
chapter treats **properties of a random sample**: sampling distributions, the behavior of
sums of independent variables, order statistics, and the convergence concepts (in
probability, in distribution, almost surely) that justify large-sample approximations. A
dedicated chapter on **principles of data reduction** — sufficiency, minimal sufficiency,
ancillarity, completeness, and the likelihood principle — is one of the book's signatures,
because it explains *why* certain statistics carry all the information about a parameter.
These chapters ground [probability.md](probability.md).

The **second half is inference itself**. Point estimation is developed through the method of
moments, maximum likelihood, and Bayes estimators, and then evaluated: unbiasedness, the
Cramér–Rao lower bound, the Rao–Blackwell and Lehmann–Scheffé theorems, and the search for
uniformly minimum-variance unbiased estimators. This is the definitive account behind
[estimation.md](estimation.md). Hypothesis testing gets its own careful development — the
Neyman–Pearson lemma, uniformly most powerful tests, likelihood-ratio tests, and the
duality between tests and confidence sets — which anchors
[hypothesis-testing.md](hypothesis-testing.md). Interval estimation, methods for evaluating
interval estimators, and a closing treatment of asymptotic evaluations round out the book,
with an appendix of the [regression](regression.md) and analysis-of-variance models that
apply the theory.

## Approach and audience

Casella & Berger is theorem-and-proof throughout, but it is not sterile: each abstract
result is tied to concrete examples and to the question "what makes an inference procedure
good?" The recurring organizing device is the likelihood function and the principles of
sufficiency and invariance — the reader learns not just how to compute an estimator or a
test, but the optimality theory that ranks one against another. It assumes solid calculus
and comfort with proof, and rewards that investment with the rigor that lighter surveys omit.
For applied and machine-learning readers, its value is as the authoritative backstop: the
place to confirm the exact assumptions under which an estimator is efficient or a test is
most powerful, complementing the applied and predictive emphasis of
[statistical-learning.md](statistical-learning.md).

## References

- [Statistical Inference, 2nd ed. — publisher page (Cengage/Duxbury)](https://www.cengage.com/c/statistical-inference-2e-casella-berger/9780534243128/)
