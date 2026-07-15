---
type: Concept
title: Game Theory
tags: [economics, game-theory, nash-equilibrium, strategy, incentives, auctions, multi-agent, ai]
timestamp: 2026-07-14
---

# Game Theory

Game theory is the mathematics of **strategic interaction**: what happens when the
best move for each agent depends on what the other agents do. Ordinary optimisation
asks "what should I choose given fixed conditions?" Game theory asks the harder
question — "what should I choose given that everyone else is *also* choosing, and
choosing in response to me?" It is the natural completion of
[marginal-thinking-and-incentives](marginal-thinking-and-incentives.md): once you accept
that agents respond to incentives, game theory works out where those mutual responses
settle.

## The anatomy of a game

Every game has three ingredients:

- **Players** — the decision-makers (people, firms, nations, algorithms).
- **Strategies** — the complete plan of action available to each player.
- **Payoffs** — the value each player receives for every *combination* of strategies.

Two-player games are usually written as a **payoff matrix**. A *strategy* dominates
another if it yields a better payoff no matter what the opponent does; a rational player
never plays a **dominated** strategy.

## Nash equilibrium

The central solution concept is the **Nash equilibrium**: a strategy profile where no
player can improve their payoff by unilaterally deviating. Everyone is playing a best
response to everyone else, so no one has a reason to move. Nash proved that every finite
game has at least one such equilibrium, possibly in **mixed strategies** (randomising
over pure moves). Equilibrium is not the same as "good outcome" — it is merely *stable*.

## The prisoner's dilemma

The most famous game shows equilibrium and welfare pulling apart. Two suspects each
choose to cooperate (stay silent) or defect (confess):

|                    | B cooperates | B defects |
|--------------------|--------------|-----------|
| **A cooperates**   | −1, −1       | −3, 0     |
| **A defects**      | 0, −3        | −2, −2    |

Defecting dominates for each player individually, so the unique Nash equilibrium is
**(defect, defect)** — worse for both than mutual cooperation. This single structure
explains arms races, price wars, overfishing, and free-riding on public goods; it is the
game-theoretic engine behind [market-failure-and-externalities](market-failure-and-externalities.md).

## Zero-sum vs. cooperative, and repetition

- **Zero-sum** games are pure conflict: one player's gain is exactly another's loss. Von
  Neumann's **minimax theorem** — one player minimises the maximum loss the other can
  inflict — solves them and anchors the whole field
  ([von-neumann-morgenstern-theory-of-games](von-neumann-morgenstern-theory-of-games.md)).
- **Cooperative / positive-sum** games allow mutual gain, the case behind
  [opportunity-cost-and-scarcity](opportunity-cost-and-scarcity.md)'s gains from trade.
- **Repeated games** change everything. When the prisoner's dilemma is played many times,
  strategies like *tit-for-tat* can sustain cooperation, because defection today invites
  punishment tomorrow. The "shadow of the future" turns a one-shot trap into a
  self-enforcing agreement — the logic behind reputations, contracts, and norms.

## Mechanism and auction design

Game theory run in reverse is **mechanism design**: instead of predicting behaviour
given the rules, you *design the rules* so that self-interested play produces the outcome
you want. Auctions are the flagship application. A **second-price (Vickrey) auction** —
the winner pays the second-highest bid — makes truthful bidding a dominant strategy, so
the designer learns everyone's true valuation. This is not academic: it is the
theoretical spine of the ad markets that fund most of the web.

## Why it matters — and the AI ties

Game theory is where economics and modern AI fuse most tightly:

- **Multi-agent reinforcement learning.** When several learning agents share an
  environment, each is doing [../ai/reinforcement-learning.md](../ai/reinforcement-learning.md)
  against a moving target — the others' evolving policies. Convergence, when it happens,
  is to an equilibrium concept, and self-play (as in AlphaGo) is repeated-game learning.
- **GANs as a minimax game.** A generative adversarial network is literally a two-player
  zero-sum game: a generator and a discriminator play minimax, and the training target is
  a Nash equilibrium. See [../ai/generative-models.md](../ai/generative-models.md).
- **Auctions and markets at scale.** Online ad auctions, spectrum auctions, and matching
  markets are mechanism design deployed on billions of transactions — increasingly with
  bidders that are themselves [../ai/machine-learning.md](../ai/machine-learning.md)
  systems, which loops back to multi-agent dynamics.
- **Alignment and adversarial robustness.** Framing training as a game between a model and
  an adversary underpins much work on robustness and safety, a recurring theme in
  [../ai-business/index.md](../ai-business/index.md).

Multi-agent economies of interacting AI systems behave as
[../systems-thinking/complex-adaptive-systems.md](../systems-thinking/complex-adaptive-systems.md):
equilibrium is emergent, not designed.

## References

- [Theory of Games and Economic Behavior](von-neumann-morgenstern-theory-of-games.md) —
  von Neumann and Morgenstern's founding text, source of the minimax theorem and expected
  utility.
