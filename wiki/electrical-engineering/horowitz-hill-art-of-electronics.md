---
type: Reference
title: "The Art of Electronics"
tags: [electronics, circuit-design, transistors, analog, op-amps, digital-electronics]
timestamp: 2026-07-14
source: https://artofelectronics.net/
---

# The Art of Electronics

*The Art of Electronics* by Paul Horowitz and Winfield Hill (third edition, Cambridge
University Press, 2015) is the standard practical reference for real-world electronic
circuit design. Unlike device-physics textbooks that derive behavior from semiconductor
equations, it teaches electronics the way a working designer thinks: with rules of thumb,
worked example circuits, and hard-won intuition about what actually works on the bench and
why. It sits between textbook and reference manual, and it is unusual in giving as much
attention to the *pitfalls* — the circuits that look right but fail — as to the correct
designs.

## Scope

The book spans analog and digital electronics across the full range a designer meets.

- **Foundations.** DC concepts — [voltage, current, resistance](electricity-and-circuits.md),
  Ohm's law, Thévenin equivalents — then AC: capacitors, inductors, impedance, RC/RL
  filters, resonance. This is the applied circuit-analysis core.
- **Discrete active devices.** Diodes, then the two great families of
  [semiconductors and transistors](semiconductors-and-transistors.md): bipolar junction
  transistors (BJTs) and field-effect transistors (FETs/MOSFETs). Rather than dwelling on
  band-gap physics, it treats the transistor as a controllable element and teaches the
  canonical building blocks — switches, amplifier stages (common-emitter/source,
  followers), current sources, and current mirrors.
- **Operational amplifiers and feedback.** The op-amp as an idealized high-gain block, and
  negative feedback as the organizing principle behind amplifiers, active filters,
  integrators, oscillators, and precision analog design.
- **Signal chains and support.** Power supplies and voltage regulation, noise and
  low-noise design, precision and low-power techniques, and high-frequency / high-speed
  layout — the "often-neglected" areas the book deliberately covers.
- **Digital and mixed-signal.** Logic families and the physical realization of
  [logic gates and Boolean hardware](logic-gates-and-boolean-hardware.md), combinational and
  sequential [digital circuits](digital-circuits.md), memory, ADCs/DACs bridging the analog
  and digital worlds, and microcontrollers with bus and interface design.

## Why it anchors the field

*The Art of Electronics* is the bridge from *understanding* a component to *designing* with
it. Where the concept notes explain what a transistor or a gate *is*, this book shows how to
choose, bias, and combine real parts into circuits that meet specifications and survive
manufacturing tolerances, temperature, and noise. It is the practitioner's counterpart to
the bottom-up computing narratives — Petzold's [Code](petzold-code.md) and
[Nand2Tetris](nisan-schocken-elements-of-computing-systems.md) treat the switch and gate as
idealized logic; Horowitz and Hill explain the messy physical devices those idealizations
sit on top of, and where the idealization breaks down.

## Related notes

- [electricity and circuits](electricity-and-circuits.md) — the DC/AC foundations the book builds on
- [semiconductors and transistors](semiconductors-and-transistors.md) — BJTs and FETs as design elements
- [logic gates and Boolean hardware](logic-gates-and-boolean-hardware.md) — logic families realizing gates physically
- [digital circuits](digital-circuits.md) — combinational and sequential design, memory, mixed-signal
- [Code (Petzold)](petzold-code.md) and [Nand2Tetris](nisan-schocken-elements-of-computing-systems.md) — the idealized-switch view this book grounds physically

## References

- [The Art of Electronics — Horowitz & Hill](https://artofelectronics.net/)
