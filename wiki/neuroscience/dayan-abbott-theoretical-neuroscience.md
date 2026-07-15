---
type: Reference
title: Theoretical Neuroscience
tags: [computational-neuroscience, theoretical-neuroscience, neural-coding, modeling, textbook, reference]
timestamp: 2026-07-14
source: https://mitpress.mit.edu/9780262541855/theoretical-neuroscience/
---

# Theoretical Neuroscience: Computational and Mathematical Modeling of Neural Systems

*Peter Dayan and L. F. Abbott.* MIT Press, 2001. This is the standard graduate text for
[computational neuroscience](computational-neuroscience.md) — the book that defined the
field's shared mathematical vocabulary. Where the empirical textbooks describe what the
brain does, Dayan and Abbott ask how to *model* it: how to write down equations for what
neurons compute and how populations of them represent, transform, and learn from
information.

## Scope and approach

The book is deliberately structured in **three parts**, moving from data to mechanism to
adaptation:

- **Part I — Neural encoding and decoding.** The core of what the field calls
  [neural coding](neural-coding.md). Encoding asks how stimuli are translated into firing
  patterns — firing rates, tuning curves, spike-train statistics, and the reverse-correlation
  methods that recover a neuron's stimulus preferences. Decoding asks the inverse: what a
  downstream reader can infer about the stimulus from the spikes, framed with estimation
  theory, discriminability, and information-theoretic bounds on how much a neural response
  can convey.
- **Part II — Neurons and networks.** Biophysical and reduced models of single cells
  (from Hodgkin-Huxley-style conductance models down to integrate-and-fire abstractions),
  then models of interconnected populations — feedforward and recurrent networks, their
  dynamics, and how their collective behavior gives rise to representations.
- **Part III — Adaptation and learning.** How synaptic strengths change:
  [synaptic plasticity](synaptic-plasticity.md) rules (Hebbian and their stabilized
  variants), unsupervised and supervised learning in neural models, and reinforcement
  learning as a theory of how the brain learns from reward.

The approach is **normative and mathematical**: it treats the brain as an
information-processing system and applies probability, linear algebra, dynamical systems,
and information theory to say what a circuit is computing and why that computation might be
useful. It is analytical rather than encyclopedic — a set of tools and worked models, not a
survey of anatomy.

## Bridge to machine learning

Theoretical neuroscience and machine learning are two branches of the same tree, and this
book sits at the fork. Its treatment of population coding, gradient-based learning rules,
and reward-driven adaptation runs directly parallel to the mathematics of
[deep learning](../ai/deep-learning.md) and [neural networks](../ai/neural-networks.md) —
often the *same* equations read with different intent (explaining biology vs. engineering a
learner). Dayan's later foundational work on reinforcement learning as a model of dopamine
signaling grew out of exactly this synthesis.

## References

- [Theoretical Neuroscience — MIT Press](https://mitpress.mit.edu/9780262541855/theoretical-neuroscience/)
- [Book page — P. Dayan (Gatsby / UCL)](http://www.gatsby.ucl.ac.uk/~dayan/book/)
