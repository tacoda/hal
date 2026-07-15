---
type: Concept
title: The Synapse and Neurotransmission
tags: [neuroscience, synapse, neurotransmitter, receptors, epsp, ipsp]
timestamp: 2026-07-14
---

# The Synapse and Neurotransmission

A **synapse** is the specialized junction where one [neuron](neuron.md) passes a signal to
another cell. **Neurotransmission** is the process of that transfer. If the
[action potential](action-potential.md) is how a neuron talks along its own length, the
synapse is how it talks *to another cell* — and because the strength of that connection is
adjustable, the synapse is the physical substrate of learning (see
[synaptic-plasticity](synaptic-plasticity.md)). In the artificial-network analogy, the
synapse is the biological counterpart of a **weight**.

## Chemical vs electrical synapses

- **Electrical synapses** connect two cells through **gap junctions** — protein channels
  that let ionic current flow directly from one cytoplasm to the next. They are fast and
  bidirectional, used where speed and synchrony matter (e.g. some interneuron networks),
  but they cannot easily amplify, invert, or reshape the signal.
- **Chemical synapses** are the dominant type and the flexible one. There is no direct
  electrical connection; the presynaptic and postsynaptic membranes are separated by a
  narrow **synaptic cleft**, and the signal is carried across it by a chemical messenger.

## The mechanism of chemical neurotransmission

1. **Arrival and Ca²⁺ influx.** An action potential reaches the axon terminal and opens
   voltage-gated **Ca²⁺ channels**. Calcium floods in.
2. **Vesicle release.** Ca²⁺ triggers synaptic vesicles — membrane sacs pre-loaded with
   **neurotransmitter** — to fuse with the membrane and dump their contents into the cleft
   (exocytosis).
3. **Receptor binding.** Transmitter molecules diffuse across and bind **receptors** on the
   postsynaptic membrane. *Ionotropic* receptors are themselves ion channels that open on
   binding (fast); *metabotropic* receptors trigger intracellular signaling cascades
   (slower, modulatory).
4. **Postsynaptic response.** Opened channels let ions flow, changing the postsynaptic
   voltage.
5. **Termination.** Transmitter is cleared by reuptake, enzymatic breakdown, or diffusion,
   resetting the synapse.

```mermaid
flowchart LR
    AP[Action potential arrives] --> Ca[Ca2+ channels open]
    Ca --> V[Vesicles fuse, release transmitter]
    V --> R[Transmitter binds postsynaptic receptors]
    R --> PSP[Ion channels open -> EPSP or IPSP]
    PSP --> Clr[Transmitter cleared, reset]
```

## Excitatory and inhibitory postsynaptic potentials

The *sign* of the effect depends on which ions the receptor gates:

- An **excitatory postsynaptic potential (EPSP)** depolarizes the postsynaptic cell,
  pushing it *toward* threshold — typically Na⁺/Ca²⁺ inflow driven by **glutamate**, the
  main excitatory transmitter.
- An **inhibitory postsynaptic potential (IPSP)** hyperpolarizes or stabilizes the cell,
  pushing it *away* from threshold — typically Cl⁻ inflow or K⁺ outflow driven by **GABA**,
  the main inhibitory transmitter.

Other transmitters (dopamine, serotonin, acetylcholine, norepinephrine) act largely as
**neuromodulators**, tuning the excitability and plasticity of whole circuits rather than
delivering fast point-to-point signals. Dopamine's role in signaling reward prediction
error connects directly to [../ai/reinforcement-learning.md](../ai/reinforcement-learning.md).

## Summation: the neuron adds it all up

A single neuron receives thousands of EPSPs and IPSPs. It **integrates** them:

- **Spatial summation** — inputs from many synapses arriving at once combine.
- **Temporal summation** — inputs arriving in quick succession pile up before decaying.

If the summed depolarization at the axon hillock crosses threshold, the neuron fires. This
weighted addition of many signed inputs, followed by a threshold, is precisely the operation
an artificial neuron performs: EPSP/IPSP magnitudes correspond to positive and negative
**weights**, summation to the dot product, and the firing threshold to the activation
function. See [neural networks](../ai/neural-networks.md).

## Why the synapse is the "weight"

Crucially, synaptic strength is **not fixed**. The amount of transmitter released and the
postsynaptic sensitivity can grow or shrink with use — the topic of
[synaptic-plasticity](synaptic-plasticity.md). A brain learns by adjusting its synapses,
just as a network learns by adjusting its weights via
[backpropagation and gradient descent](../ai/backpropagation-and-gradient-descent.md).
That parallel — adjustable connection strengths as the seat of learning — is the deepest
link between the two fields, even though the biological update rule is local and
mechanistically unlike gradient descent.

## Canonical example: the neuromuscular junction

The **neuromuscular junction**, where a motor neuron meets a muscle fiber, is the
best-understood chemical synapse. Acetylcholine released from the terminal opens receptor
channels on the muscle, depolarizing it and triggering contraction — the clean model system
in which vesicular release and receptor action were first worked out.

## References

- [Kandel, *Principles of Neural Science*](kandel-principles-of-neural-science.md)
- [Purves, *Neuroscience*](purves-neuroscience.md)
- [Dayan & Abbott, *Theoretical Neuroscience*](dayan-abbott-theoretical-neuroscience.md)
