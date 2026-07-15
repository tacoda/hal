---
type: Reference
title: "Computer Organization and Design: The Hardware/Software Interface"
tags: [computer-science, computer-architecture, isa, pipelining, memory-hierarchy, caches, performance, foundations]
timestamp: 2026-07-14
source: https://www.elsevier.com/books/computer-organization-and-design-mips-edition/patterson/978-0-12-820109-1
---

# Computer Organization and Design: The Hardware/Software Interface

By David A. Patterson and John L. Hennessy (Morgan Kaufmann/Elsevier; 6th ed.
2020, MIPS edition; also RISC-V and ARM editions). The standard undergraduate
computer-architecture textbook — the companion to the authors' graduate *Computer
Architecture: A Quantitative Approach*. Its subtitle names its thesis: architecture
is the **hardware/software interface**, and you cannot reason well about either side
without understanding the contract between them.

The book is built around **eight great ideas** the authors return to throughout —
including *design for Moore's Law*, *make the common case fast*, *use parallelism*,
*use pipelining*, *predict*, and the *memory hierarchy* — as a set of reusable
principles rather than isolated facts. It is the anchor reference for
[computer-architecture.md](computer-architecture.md).

## Performance: what "fast" actually means

Before any hardware, the book fixes the vocabulary. CPU time decomposes as:

> time = instructions × cycles-per-instruction (CPI) × clock-cycle-time

This equation is the recurring scoreboard: every architectural technique in the book
is justified by which factor it improves. It also debunks single-number benchmarks
(clock speed alone, MIPS) and motivates Amdahl's Law — the speedup from improving one
part is capped by the fraction of time spent in that part, the same ceiling that
bounds parallel programs in
[concurrency-and-parallelism.md](concurrency-and-parallelism.md).

## The instruction set architecture (ISA)

The ISA is the interface itself: the set of instructions the hardware promises to
execute and the software targets. Using MIPS (a clean RISC ISA) the book covers
instruction formats, addressing modes, procedure calls and the stack, and how
high-level constructs compile down to machine code — which is exactly where this
book meets the back end of the
[aho-dragon-book-compilers.md](aho-dragon-book-compilers.md) and the trap/interrupt
machinery relied on by [operating-systems.md](operating-systems.md).

## The processor: datapath, control, and pipelining

The heart of the book is *building* a processor:

- A **single-cycle datapath and its control** for a subset of MIPS — showing how
  registers, ALU, and memory wire together and how control signals steer them.
- **Pipelining** — overlapping the fetch/decode/execute/memory/write-back stages so
  a new instruction starts each cycle. This raises throughput but introduces
  **hazards**: structural, data (solved by forwarding/bypassing and stalls), and
  **control hazards** from branches (solved by **branch prediction**).
- A tour of how real machines push further with deeper pipelines, superscalar
  issue, and out-of-order execution.

```mermaid
flowchart LR
    IF[Fetch] --> ID[Decode] --> EX[Execute] --> MEM[Memory] --> WB[Write-back]
```

## The memory hierarchy

Because fast memory is small and large memory is slow, real systems layer them:
registers → caches (L1/L2/L3) → main memory → disk. The book teaches **caching** from
first principles — locality (temporal and spatial), block placement/replacement,
write policies, and the average-memory-access-time model — then **virtual memory** and
the TLB, connecting directly to the paging machinery in
[operating-systems.md](operating-systems.md). "Make the common case fast" is the memory
hierarchy in one sentence.

## Parallelism

Later chapters address the multicore era: instruction-level, data-level (SIMD/GPU),
and thread-level parallelism, cache coherence for shared-memory multiprocessors, and
the hardware side of the software concurrency covered in
[concurrency-and-parallelism.md](concurrency-and-parallelism.md).

## Why it belongs in this wiki

This is the book that makes the machine concrete — how an instruction actually runs,
why programs have the performance they do, and what the OS is really controlling. It
is the layer directly beneath [operating-systems.md](operating-systems.md) and the
target that [compilers](aho-dragon-book-compilers.md) generate code for.

## References

- [Computer Organization and Design (MIPS Edition, 6th ed.) — Patterson & Hennessy](https://www.elsevier.com/books/computer-organization-and-design-mips-edition/patterson/978-0-12-820109-1)
