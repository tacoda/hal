---
type: Index
title: Computer Science
tags: [computer-science, algorithms, systems, theory, index]
timestamp: 2026-07-14
---

# Computer Science

What can be computed, how, and at what cost — from the theory of computation down through
the machine and up to databases and networks. This folder is the college-level core. It
rests on [mathematics](../math/index.md) and [logic](../logic/index.md) (its theory side)
and feeds [artificial intelligence](../ai/index.md),
[distributed systems](../distributed-systems/index.md), and
[software engineering](../software-engineering/index.md).

## The shape of the field

**Theory** asks what is computable and how hard: [theory of computation](theory-of-computation.md)
(automata → Turing machines, the Chomsky hierarchy, the halting problem) and
[computational complexity](computational-complexity.md) (big-O, P vs NP, NP-completeness).
**Programs** are built from [algorithms](algorithms.md) over
[data structures](data-structures.md), expressed in
[programming languages](programming-languages-and-paradigms.md) and translated by
[compilers and interpreters](compilers-and-interpreters.md). **Systems** run them:
[operating systems](operating-systems.md) manage resources over a
[computer architecture](computer-architecture.md), talk over
[computer networks](computer-networks.md), persist state in [databases](databases.md), and
must handle [concurrency and parallelism](concurrency-and-parallelism.md). The theory side
overlaps [logic](../logic/computability-and-decidability.md); the systems side flows into
[distributed systems](../distributed-systems/index.md).

## Concepts

- [Theory of Computation](theory-of-computation.md) — automata, formal languages, Turing machines, the Chomsky hierarchy, the halting problem
- [Computational Complexity](computational-complexity.md) — big-O/Θ/Ω, P and NP, reductions, NP-completeness, P vs NP
- [Algorithms](algorithms.md) — design paradigms (divide & conquer, greedy, DP, backtracking), correctness, sorting/searching, graph algorithms
- [Data Structures](data-structures.md) — arrays, lists, hash tables, trees, heaps, graphs; the time/space trade-offs
- [Programming Languages and Paradigms](programming-languages-and-paradigms.md) — imperative/OO/functional/logic, type systems, semantics, memory management
- [Compilers and Interpreters](compilers-and-interpreters.md) — lex → parse → semantic analysis → IR → optimize → codegen; compiler vs interpreter vs JIT
- [Operating Systems](operating-systems.md) — processes & threads, scheduling, virtual memory, file systems, the user/kernel boundary
- [Computer Architecture](computer-architecture.md) — the von Neumann model, ISA, pipelining, the memory hierarchy and caching
- [Computer Networks](computer-networks.md) — the layered TCP/IP model, packet switching, IP/TCP/UDP, DNS, HTTP
- [Databases](databases.md) — the relational model, SQL, ACID transactions, indexing, normalization
- [Concurrency and Parallelism](concurrency-and-parallelism.md) — threads/processes, shared memory vs message passing, races, locks, deadlock, atomicity

## Canonical works

- [Introduction to Algorithms](introduction-to-algorithms.md) — Cormen, Leiserson, Rivest, Stein (CLRS)
- [Structure and Interpretation of Computer Programs](sicp.md) — Abelson & Sussman (SICP)
- [Introduction to the Theory of Computation](sipser-theory-of-computation.md) — Michael Sipser
- [Operating Systems: Three Easy Pieces](ostep-operating-systems.md) — Arpaci-Dusseau (free)
- [Computer Organization and Design](patterson-hennessy-computer-organization.md) — Patterson & Hennessy
- [Computer Networking: A Top-Down Approach](kurose-ross-computer-networking.md) — Kurose & Ross
- [Database System Concepts](silberschatz-database-system-concepts.md) — Silberschatz, Korth, Sudarshan
- [Compilers: Principles, Techniques, and Tools](aho-dragon-book-compilers.md) — Aho, Lam, Sethi, Ullman (Dragon Book)

## Related fields

[Mathematics](../math/index.md) (discrete math, graph theory), [logic](../logic/index.md)
(computability, Boolean algebra), [artificial intelligence](../ai/index.md),
[distributed systems](../distributed-systems/index.md), and
[software engineering](../software-engineering/index.md).
