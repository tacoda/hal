---
type: Reference
title: Neuronal Dynamics
tags: [computational-neuroscience, spiking-neurons, integrate-and-fire, network-dynamics, modeling, textbook, reference]
timestamp: 2026-07-14
source: https://neuronaldynamics.epfl.ch/
---

# Neuronal Dynamics: From Single Neurons to Networks and Models of Cognition

*Wulfram Gerstner, Werner M. Kistler, Richard Naud, and Liam Paninski.* Cambridge
University Press, 2014; the full text is freely available online at
neuronaldynamics.epfl.ch, with accompanying Python exercises and video lectures. Aimed at
advanced undergraduates and beginning graduate students, it is a modern, up-to-date
introduction to [computational neuroscience](computational-neuroscience.md) built around a
single question it poses at the outset: *what triggers a neuron to send out a signal, and
what is the neural code?*

## Scope and approach

The title names the trajectory: the book climbs from **single neurons** to **networks** to
**models of cognition**, keeping spiking dynamics — not just firing rates — at the center
throughout.

- **Single-neuron models.** It develops the biophysics of the
  [action potential](action-potential.md) from the Hodgkin-Huxley conductance model, then
  reduces it through a ladder of simplifications: two-dimensional phase-plane models,
  the leaky integrate-and-fire neuron, and the more general Spike Response Model. A recurring
  theme is *how much* biological detail a model needs, and generalized integrate-and-fire
  models are shown to predict real spike times well.
- **Noise and variability.** Spike trains are treated as stochastic — the book covers the
  statistics of firing, noise models, and how variability shapes what the
  [neural code](neural-coding.md) can carry.
- **Network dynamics.** How populations of spiking neurons behave collectively:
  the dynamics of large [neural circuits](neural-circuits.md), oscillations,
  asynchronous and synchronous firing states, and mean-field descriptions of population
  activity.
- **Plasticity and cognition.** [Synaptic plasticity](synaptic-plasticity.md), including
  spike-timing-dependent plasticity, and how learning and memory, decision-making, and
  other cognitive functions can emerge from networks of spiking units.

The approach is **dynamical-systems-driven and rigorous but accessible**: it favors
tractable reduced models over full biophysical detail, pairs each idea with intuition, and
makes the mathematics runnable through its Python exercises. It complements
[Dayan and Abbott](dayan-abbott-theoretical-neuroscience.md) — where they emphasize
encoding/decoding and rate-based population coding, Gerstner et al. foreground the *spike*
and the temporal dynamics of firing.

## Relation to artificial networks

Spiking-neuron models are the biological ground truth that
[artificial neural networks](../ai/neural-networks.md) abstract away: the smooth activation
of an ANN unit stands in for the all-or-none spike this book models in detail. The renewed
interest in spiking and event-driven computation makes *Neuronal Dynamics* a natural bridge
between neuroscience and the engineering of learning systems.

## References

- [Neuronal Dynamics (free online text, exercises, lectures) — EPFL](https://neuronaldynamics.epfl.ch/)
