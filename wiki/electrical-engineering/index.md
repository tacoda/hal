---
type: Index
title: Electrical Engineering & How a Computer Works
tags: [electrical-engineering, hardware, computers, index]
timestamp: 2026-07-14
---

# Electrical Engineering & How a Computer Works

A focused field: **how a computer physically works, from the electron up to the operating
system** — the layer that stacks *under* all of HAL's software content. The spine is one
chain: **electron → switch → gate → bit → CPU → the OS handoff**. It grounds
[computer science](../computer-science/computer-architecture.md) in physical reality,
picking up where [physics](../physics/electromagnetism.md) leaves off and handing off to
[operating systems](../operating-systems/index.md).

## The chain, bottom to top

Electricity moves electrons through [circuits](electricity-and-circuits.md). A
[semiconductor transistor](semiconductors-and-transistors.md) makes a controllable
**switch**; switches wire into [logic gates](logic-gates-and-boolean-hardware.md) that make
[Boolean algebra](../logic/boolean-algebra.md) physical; gates compose into
[digital circuits](digital-circuits.md) that compute and remember. Two voltage levels
become the [bit](binary-and-data-representation.md), and bits become all data. Gates and
memory assemble into the [CPU and datapath](cpu-and-datapath.md) running the
fetch-decode-execute cycle, with [memory & storage hardware](memory-and-storage-hardware.md)
holding the bits. At the top, the [hardware/software boundary](hardware-software-boundary.md)
— the instruction set, firmware, interrupts, and boot — hands control to the operating
system, where the software stack begins.

## Concepts

- [Electricity and Circuits](electricity-and-circuits.md) — the electron as charge carrier: voltage, current, resistance, Ohm's law, power
- [Semiconductors and Transistors](semiconductors-and-transistors.md) — doping, the diode, the MOSFET as the switch that is the atom of computing
- [Logic Gates and Boolean Hardware](logic-gates-and-boolean-hardware.md) — AND/OR/NOT/NAND from transistors; NAND as universal; Boolean algebra in silicon
- [Digital Circuits](digital-circuits.md) — combinational (adders, muxes) and sequential (flip-flops, registers, the clock) logic
- [Binary and Data Representation](binary-and-data-representation.md) — the bit, two's complement, floating point, encoding text/color/sound
- [CPU and Datapath](cpu-and-datapath.md) — ALU, registers, buses, control unit, clock, fetch-decode-execute; the instruction set
- [Memory and Storage Hardware](memory-and-storage-hardware.md) — SRAM/DRAM, the memory hierarchy, flash/disk/ROM, addressing
- [The Hardware/Software Boundary](hardware-software-boundary.md) — the ISA contract, machine code, firmware, interrupts, boot → the OS handoff

## Canonical works

- [Code: The Hidden Language](petzold-code.md) — Charles Petzold; switches → CPU, the perfect electron→bit narrative
- [The Elements of Computing Systems (Nand2Tetris)](nisan-schocken-elements-of-computing-systems.md) — Nisan & Schocken; NAND → full computer & OS
- [The Art of Electronics](horowitz-hill-art-of-electronics.md) — Horowitz & Hill; the practical electronics classic

## Related fields

[Physics](../physics/electromagnetism.md) (fields, semiconductors, quantum),
[logic](../logic/boolean-algebra.md) (Boolean algebra realized in gates),
[computer science](../computer-science/computer-architecture.md) (architecture, above this layer),
and [operating systems](../operating-systems/index.md) (where the software stack takes over).
