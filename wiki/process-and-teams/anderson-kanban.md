---
type: Reference
title: "Kanban: Successful Evolutionary Change for Your Technology Business"
tags: [kanban, flow, wip-limits, evolutionary-change, knowledge-work, lean]
timestamp: 2026-07-14
source: https://kanbanbooks.com/kanban-successful-evolutionary-change-for-your-technology-business/
---

# Kanban: Successful Evolutionary Change for Your Technology Business

David J. Anderson's 2010 book (Blue Hole Press), the work that adapted the Toyota
manufacturing *kanban* signal into a management method for software and knowledge work.
Its central bet is that most organizations fail at process change because they impose a
new process wholesale and hit resistance. Kanban instead **starts with what you do now**
and applies pressure for *evolutionary*, incremental improvement — no new roles, no
prescribed ceremonies, no reorganization on day one. This is the deep contrast with a
framework like [Scrum](scrum.md), which defines a fixed set of roles and events. The book
anchors the concept note on [kanban and flow](kanban-and-flow.md).

## The core idea: visualize, limit WIP, manage flow

Kanban treats knowledge work as an invisible flow of items and makes it visible and
governable:

1. **Visualize the workflow** — a board with a column per process stage, cards for work
   items, so the whole system is seen at once.
2. **Limit work-in-progress (WIP)** — an explicit cap on how many items may occupy each
   stage. This is the mechanism that changes everything: WIP limits force finishing over
   starting, expose bottlenecks, and cut multitasking.
3. **Manage flow** — watch how items move, minimize the time from commitment to delivery,
   smooth out stalls and queues.
4. **Make process policies explicit** — the rules for how work is pulled and done are
   written down where everyone can see and challenge them.
5. **Implement feedback loops** — regular cadences to review the system and adapt.
6. **Improve collaboratively, evolve experimentally** — use models (flow, queuing theory)
   to guide change and improve by consensus.

```mermaid
flowchart LR
    Backlog[Backlog] --> Todo["Ready (WIP≤3)"]
    Todo --> Dev["In progress (WIP≤2)"]
    Dev --> Review["Review (WIP≤2)"]
    Review --> Done[Done]
    Dev -. blocked, pull nothing new .-> Todo
```

A **pull system** underlies it: a downstream stage with free capacity *pulls* the next
item, rather than an upstream stage *pushing* work forward. This is Little's Law made
operational — limit WIP and average lead time falls in proportion, so delivery becomes
faster and more predictable.

## Why it matters

Because it overlays existing process, Kanban lowers the political cost of change and suits
teams that can't (or shouldn't) adopt time-boxed sprints — operations, support,
maintenance, or any interrupt-driven flow. It shares its intellectual roots with
[lean software development](lean-software-development.md) and the broader lean tradition,
and it delivers on the [agile manifesto](agile-manifesto.md)'s principles of frequent
delivery and sustainable pace. Its outcome-oriented, flow-metric mindset (lead time,
throughput, cycle time) feeds directly into [product discovery and delivery](product-discovery-and-delivery.md)
and the emphasis on [outcomes over output](outcomes-over-output.md). Many teams run Kanban
*and* Scrum together ("Scrumban"), and flow health is a standing concern for
[product management](../business/product-management.md).

## References

- [Kanban: Successful Evolutionary Change for Your Technology Business — kanbanbooks.com](https://kanbanbooks.com/kanban-successful-evolutionary-change-for-your-technology-business/)
