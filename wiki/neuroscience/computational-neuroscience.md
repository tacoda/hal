---
type: Concept
title: Computational Neuroscience
tags: [neuroscience, modeling, hodgkin-huxley, integrate-and-fire, firing-rate, ann]
timestamp: 2026-07-14
---

# Computational Neuroscience

**Computational neuroscience** builds mathematical models of the nervous system to explain
*how* neural activity produces computation. Where anatomy asks what connects to what,
computational neuroscience writes down equations — usually
[differential equations](../math/differential-equations.md) — for how membrane voltage,
firing rates, and synaptic weights evolve in time, then tests whether the model reproduces
what real [neurons](neuron.md) and [circuits](neural-circuits.md) do. It is also the field
where neuroscience and artificial [neural networks](../ai/neural-networks.md) meet most
directly, in a genuinely two-way exchange of ideas.

## Levels of neuron model

Models trade biological detail against tractability:

- **Hodgkin–Huxley (biophysical).** The gold standard, and a Nobel-winning achievement: a
  set of coupled nonlinear [differential equations](../math/differential-equations.md)
  describing how voltage-gated sodium and potassium conductances generate the
  [action potential](action-potential.md). Faithful but expensive — you model the ion
  channels themselves.

  $$C_m \frac{dV}{dt} = -g_{Na}m^3h(V - E_{Na}) - g_K n^4 (V - E_K) - g_L(V - E_L) + I$$

- **Integrate-and-fire (spiking, reduced).** Abstract away the channels: treat the neuron
  as a capacitor that integrates input current until voltage crosses a threshold, emits a
  spike, and resets. A single leaky equation

  $$\tau_m \frac{dV}{dt} = -(V - V_{rest}) + R\,I(t)$$

  captures spike *timing* cheaply enough to simulate large [circuits](neural-circuits.md).
- **Firing-rate models.** Drop individual spikes entirely and track a neuron's *rate* of
  firing as a continuous variable. A population's rates evolve by an equation whose form —
  weighted sum of inputs passed through a nonlinearity — is essentially the equation of an
  artificial [neural network](../ai/neural-networks.md) unit. This is the level at which the
  bridge to AI is tightest.

## The two-way street with artificial networks

Artificial neural nets began as a firing-rate abstraction of biology (McCulloch–Pitts,
the perceptron), and [deep learning](../ai/deep-learning.md) inherited several ideas from
the brain:

- **Hierarchical feature detection** from the [visual cortex](sensory-systems.md) →
  [convolutional networks](../ai/convolutional-neural-networks.md).
- **Recurrence for temporal memory** from cortical [circuits](neural-circuits.md) →
  [RNNs](../ai/sequence-models-and-rnns.md).
- **Reward-driven learning** from dopamine → [reinforcement learning](../ai/reinforcement-learning.md).
- **Learning by adjusting connection strengths** from
  [synaptic plasticity](synaptic-plasticity.md) → weight updates.

But deep learning conspicuously **did not** take much else, and the differences are the
interesting part:

- **Backpropagation is biologically implausible** — the brain has no obvious mechanism to
  ship exact global error gradients backward across synapses; it likely uses more local
  learning rules.
- **Real neurons spike**; most artificial units emit continuous rates.
- **The brain is massively recurrent and runs on ~20 watts**; large models are largely
  feedforward and enormously power-hungry.
- **Biology learns online from few examples**; models train offline on vast data.

So the artificial "neural network" is a loose, useful caricature — inspired by the brain,
not a copy of it. Computational neuroscience is where that gap is measured precisely rather
than hand-waved.

## Why it matters

Modeling forces theories to be explicit and falsifiable: a verbal story about a circuit
becomes a system of equations you can simulate and compare against recordings. For AI, the
field is the principled channel through which biological insight enters — and a reality
check on which brain-inspired claims actually hold. It draws on
[differential equations](../math/differential-equations.md), dynamical systems, and
probability, and it is where ideas like [predictive coding](predictive-coding-and-cognition.md)
get their mathematical spine.

## References

- [Dayan & Abbott, *Theoretical Neuroscience*](dayan-abbott-theoretical-neuroscience.md) —
  the standard graduate text on modeling neurons and networks.
- [Gerstner et al., *Neuronal Dynamics*](gerstner-neuronal-dynamics.md) — spiking neuron
  models from integrate-and-fire to networks.
