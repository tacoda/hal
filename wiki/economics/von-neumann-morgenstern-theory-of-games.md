---
type: Reference
title: Theory of Games and Economic Behavior
tags: [economics, game-theory, expected-utility, minimax, von-neumann]
timestamp: 2026-07-14
source: https://press.princeton.edu/books/paperback/9780691130613/theory-of-games-and-economic-behavior
---

# Theory of Games and Economic Behavior

*Theory of Games and Economic Behavior* (1944), by mathematician John von Neumann and
economist Oskar Morgenstern, is the founding work of [game theory](game-theory.md) and
the book that put the strategic analysis of interacting agents on a formal mathematical
footing. It grew out of von Neumann's 1928 paper "Zur Theorie der Gesellschaftsspiele"
("On the Theory of Board Games") and Morgenstern's conviction that economics needed the
same rigor.

## Central ideas

- **Games as models of interaction.** The book reframes economic and social situations as
  *games*: a set of players, the strategies available to each, and payoffs that depend on
  everyone's choices jointly. This shifts the object of study from a single optimizing
  agent to the coupling of many agents' decisions — the problem
  [microeconomics](microeconomics.md) had struggled to formalize.
- **The minimax theorem.** For two-person zero-sum games (one player's gain is exactly the
  other's loss), von Neumann's minimax theorem guarantees a well-defined value: each player
  can guarantee an outcome by playing the strategy that minimizes their maximum possible
  loss, and these guarantees meet. This is the book's mathematical cornerstone.
- **Mixed strategies.** Optimal play often requires randomizing over actions rather than
  committing to one — a mixed strategy — which is what makes the minimax value attainable.
- **Expected utility.** An appendix added to the 1947 second edition derives the
  von Neumann–Morgenstern utility theorem from a small set of axioms on rational
  preferences over risky prospects: an agent whose preferences satisfy the axioms behaves
  *as if* maximizing the expectation of a utility function. This gave decision-under-risk
  its standard normative model — the benchmark that later
  [behavioral economics](behavioral-economics.md) would test and challenge.
- **Coalitions and cooperative games.** Much of the book treats *n*-player cooperative
  games, where players can form coalitions and bargain over how to split gains, introducing
  solution concepts for coalition formation.

## Influence

The founding minimax and expected-utility framework seeded the whole modern field: Nash's
non-cooperative equilibrium extended the analysis beyond zero-sum games, and the tools now
underpin economics, evolutionary biology, and computer science. In artificial intelligence,
the same value-of-a-game idea and sequential decision-making run directly into
[reinforcement learning](../ai/reinforcement-learning.md), where an agent learns a policy
by optimizing expected long-run reward, and into multi-agent and adversarial (minimax)
search.

## References

- [Theory of Games and Economic Behavior — Princeton University Press](https://press.princeton.edu/books/paperback/9780691130613/theory-of-games-and-economic-behavior)
