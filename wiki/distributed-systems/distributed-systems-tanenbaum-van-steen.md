---
type: Reference
title: "Distributed Systems (Tanenbaum & van Steen)"
tags: [distributed-systems, textbook, architectures, consistency, replication, fault-tolerance, naming, coordination]
timestamp: 2026-07-14
source: https://www.distributed-systems.net/index.php/books/ds4/
---

# Distributed Systems (Tanenbaum & van Steen)

The standard undergraduate/early-graduate textbook on distributed systems, by
Maarten van Steen and Andrew S. Tanenbaum. The fourth edition (v4.03, January
2025) is offered as a free personalized digital download from the authors' site,
alongside a full slide deck and runnable Python 3 code examples; a print edition is
sold through Amazon. The book's method is to introduce a general principle and then
ground it in a fragment of a real system — the fourth edition threads blockchain
systems through the text as one such running example.

## Scope

The book is organized around the recurring problems every distributed system must
solve, roughly one chapter per problem. It builds from a definition of what a
distributed system *is* — a collection of independent computers that presents itself
to users as a single coherent system — and the goals (resource sharing, transparency,
openness, scalability) and pitfalls (the fallacies of distributed computing: assuming
the network is reliable, latency is zero, bandwidth is infinite, etc.). See
[distributed-systems-fundamentals.md](distributed-systems-fundamentals.md) for these
foundational framings.

The core topics it develops:

- **Architectures** — architectural styles (layered, object-based, event-based,
  resource-centered/REST) and system architectures (client–server, peer-to-peer,
  structured and unstructured overlays). How the software is decomposed and where the
  components sit.
- **Processes** — threads, virtualization, clients and servers, code migration, and
  how processes are organized to do work across machines.
- **Communication** — the layered network model, remote procedure call (RPC),
  message-oriented (queued) communication, and multicast. The mechanics of getting
  bytes and requests between machines.
- **Naming** — flat, structured, and attribute-based naming; name resolution;
  locating mobile entities. How you refer to a thing when it can move and be
  replicated.
- **Coordination** — clock synchronization, logical clocks, mutual exclusion, election
  algorithms, and gossip-based coordination. See
  [time-clocks-and-causality.md](time-clocks-and-causality.md) and
  [consensus.md](consensus.md) for the ideas this chapter anchors.
- **Consistency and replication** — why you replicate (performance and reliability),
  the tension replication creates, and the spectrum of consistency models used to
  tame it: sequential, causal, eventual, and client-centric consistency, plus the
  protocols that implement them. This is the material at the heart of
  [consistency-models.md](consistency-models.md) and
  [replication.md](replication.md).
- **Fault tolerance** — failure models, process resilience through replicated groups,
  reliable client–server and group communication, distributed commit (two-phase and
  three-phase commit), and recovery via checkpointing and logging. The subject of
  [fault-tolerance-and-failure.md](fault-tolerance-and-failure.md).
- **Security** — secure channels, access control, and key management in a
  distributed setting.

## Why it anchors the field

The value of the book is less any single algorithm and more the *map*: it names the
problem categories, shows that they recur across wildly different systems, and gives a
common vocabulary (transparency, scalability, consistency model, failure model) that
the more specialized works — the Cachin algorithms text, the Raft paper — then refine.
It is the recommended first pass over the whole territory before drilling into
consensus, replication protocols, or Byzantine fault tolerance.

## References

- [Distributed Systems, 4th ed. — distributed-systems.net](https://www.distributed-systems.net/index.php/books/ds4/)
