---
type: Index
title: Distributed Systems
tags: [distributed-systems, consistency, consensus, reliability, index]
timestamp: 2026-07-14
---

# Distributed Systems

Building one coherent system out of many computers connected by an unreliable network —
where components fail independently, there is no shared clock, and the network can drop or
delay anything. This folder is the college-level core. It extends
[computer science](../computer-science/index.md) (networks, concurrency, databases), and
it is the discipline HAL's [harness engineering](../harness-engineering/index.md) keeps
rediscovering — [loop engineering is distributed-systems engineering](../harness-engineering/loop-engineering-is-just-software-engineering.md),
and [the double-booked flight](../harness-engineering/hightower-the-retry.md) is a
delivery-semantics bug.

## The shape of the field

Start with the [fundamentals](distributed-systems-fundamentals.md) — partial failure, no
global clock, the fallacies of distributed computing. Because the network can partition,
the [CAP theorem](cap-theorem.md) forces a choice, and systems pick a point on the
[consistency spectrum](consistency-models.md), which requires ordering events via
[clocks and causality](time-clocks-and-causality.md) and agreement via
[consensus](consensus.md) (Paxos, Raft). Data is spread by
[replication](replication.md) and [partitioning](partitioning-and-sharding.md);
correctness across nodes needs [distributed transactions](distributed-transactions.md) and
[fault tolerance](fault-tolerance-and-failure.md) (idempotence, retries, delivery
guarantees). Systems talk through [messaging and event streaming](messaging-and-event-streaming.md)
and compute at scale via [distributed data processing](distributed-data-processing.md).

## Concepts

- [Distributed Systems Fundamentals](distributed-systems-fundamentals.md) — partial failure, no shared clock, asynchrony, partitions, the fallacies
- [Consistency Models](consistency-models.md) — strong → eventual: linearizable, sequential, causal, read-your-writes
- [CAP Theorem](cap-theorem.md) — consistency vs availability under partition; the PACELC extension
- [Consensus](consensus.md) — agreement despite failure: FLP, Paxos, Raft, quorums, Byzantine fault tolerance
- [Time, Clocks, and Causality](time-clocks-and-causality.md) — physical skew, Lamport and vector clocks, happens-before, hybrid clocks
- [Replication](replication.md) — single-leader/multi-leader/leaderless; sync vs async; replication lag
- [Partitioning and Sharding](partitioning-and-sharding.md) — key-range vs hash, rebalancing, hot spots, routing
- [Distributed Transactions](distributed-transactions.md) — 2PC and its blocking, sagas, distributed isolation, exactly-once as idempotence
- [Fault Tolerance and Failure](fault-tolerance-and-failure.md) — failure detection, redundancy/failover, delivery guarantees, retries with backoff
- [Messaging and Event Streaming](messaging-and-event-streaming.md) — queues vs pub/sub, the durable log, delivery guarantees, backpressure
- [Distributed Data Processing](distributed-data-processing.md) — batch/MapReduce vs stream, dataflow, shuffle, windowing, exactly-once

## Canonical works

- [Designing Data-Intensive Applications](designing-data-intensive-applications.md) — Martin Kleppmann (DDIA)
- [Distributed Systems](distributed-systems-tanenbaum-van-steen.md) — Tanenbaum & van Steen (free)
- [Introduction to Reliable and Secure Distributed Programming](reliable-secure-distributed-programming-cachin.md) — Cachin, Guerraoui, Rodrigues
- [In Search of an Understandable Consensus Algorithm (Raft)](raft-consensus-paper.md) — Ongaro & Ousterhout
- [Enterprise Integration Patterns](enterprise-integration-patterns.md) — Hohpe & Woolf
- [Designing Distributed Systems](designing-distributed-systems.md) — Brendan Burns
- [Kubernetes: Up and Running](kubernetes-up-and-running.md) — Burns, Beda, Hightower
- [The Twelve-Factor App](twelve-factor-app.md) · [The Outbox Pattern](outbox-pattern.md) · [HTTP QUERY Method](http-query-method.md)

## Related fields

[Computer science](../computer-science/index.md) (networks, concurrency, databases),
[systems thinking](../systems-thinking/index.md) (feedback, resilience),
[harness engineering](../harness-engineering/index.md) (durable execution, retries),
[software architecture](../software-architecture/index.md) (microservices), and
[DevOps & SRE](../devops-sre/index.md).
