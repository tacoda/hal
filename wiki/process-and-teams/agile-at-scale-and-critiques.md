---
type: Concept
title: Agile at Scale and Critiques
tags: [agile, scaling, safe, less, spotify-model, critique, cargo-cult, process]
timestamp: 2026-07-14
---

# Agile at Scale and Critiques

[Agile](agile-and-the-agile-manifesto.md) was formulated for small, co-located teams. The
moment an organization has dozens or hundreds of teams that must ship a coherent product
together, new problems appear — dependencies, shared roadmaps, portfolio funding,
architectural alignment — that a single team's [Scrum](scrum.md) board never had to solve.
"Agile at scale" is the family of frameworks that try to answer this, and it is also the
site of the sharpest and most warranted criticism of the whole agile movement. An honest
treatment needs both halves.

## The scaling frameworks

**SAFe (Scaled Agile Framework)** is the most prescriptive and most adopted. It layers team,
program, large-solution, and portfolio levels, and coordinates teams through the *Agile
Release Train* — a set of teams that plan together in a big *PI (Program Increment)
Planning* event every ~10 weeks. Its defenders value the explicit structure and the common
vocabulary for a large enterprise; its critics argue the layers and roles reintroduce
exactly the top-down, plan-heavy machinery agile was a reaction against.

**LeSS (Large-Scale Scrum)** takes the opposite posture: keep regular Scrum and add as
little as possible, scaling by having multiple teams work off *one* Product Backlog and one
Product Owner, integrating frequently. It is minimal and principle-driven, which is its
strength and its difficulty — it offers less scaffolding to lean on.

The **"Spotify model"** (squads, tribes, chapters, guilds) escaped from a 2012 pair of blog
posts describing how Spotify organized *at that time*. It was never a framework and Spotify
itself has said it was aspirational and did not fully work as described, yet it was widely
copied as if it were a finished recipe — the clearest case of adopting a structure without
its context.

| Framework | Stance | Strength | Risk |
|---|---|---|---|
| SAFe | Prescriptive, many layers | Structure, common language | Bureaucracy; agile in name only |
| LeSS | Minimal, one backlog | Stays close to Scrum principles | Little scaffolding; hard |
| Spotify model | Descriptive snapshot | Vocabulary for org structure | Copied as a recipe it never was |

Team-boundary design is arguably a more durable lens than any of these: [Team
Topologies](../devops-sre/team-topologies.md) attacks the scaling problem structurally —
small long-lived teams, limited cognitive load, and well-defined interaction modes — rather
than by adding process layers.

## The critiques

The criticism is not fringe; several original Manifesto signatories have made it forcefully.

- **The agile-industrial complex.** A large ecosystem of certifications, tooling, and
  consultancies now sells "agile" as a product. The incentive is to sell more process, which
  drifts away from the Manifesto's own preference for *individuals and interactions over
  processes and tools*. Andy Hunt (a signatory) coined *GROWS* partly out of frustration
  that agile had become a commodity.
- **Cargo-cult / dark agile.** Teams perform the ceremonies — standups, sprints, story
  points, retros — while missing the point entirely: a standup that is a status report to a
  manager, a retro with no follow-through, a "sprint" that is just a two-week waterfall
  segment. The rituals are visible and easy to mandate; the underlying values are invisible
  and easy to skip.
- **Process over principles.** When "being agile" becomes measured by adherence to a
  framework's rules, the framework has replaced the principle it was meant to serve — the
  exact inversion the Manifesto warned against. Dave Thomas's essay *"Agile is Dead (Long
  Live Agility)"* argues the noun "Agile" has been so co-opted that only the verb — keep
  improving, in small steps, guided by feedback — is worth keeping.
- **Ceremonies as theater.** Estimation rituals that produce false precision (see
  [estimation and planning](estimation-and-planning.md)), velocity used as a productivity
  target rather than a planning aid, and retros that never change anything are all common —
  ceremony performed for the appearance of agility, delivering none of it.
- **Weaponized against workers.** "Agile" is sometimes used to justify surveillance
  (velocity as a whip), permanent crunch (everything is always urgent), or removing the
  slack and autonomy that made the original teams effective — the opposite of the
  people-first stance in [team dynamics and psychological
  safety](team-dynamics-and-psychological-safety.md).

## The honest tradeoffs

The critiques do not mean scaling is unnecessary — coordination at scale is a real problem,
and "just do small-team Scrum everywhere" ignores genuine cross-team dependencies. The
defensible reading:

- **Principles scale better than frameworks.** Short feedback loops, small batches, working
  software, and close customer contact are what [Accelerate](../devops-sre/accelerate.md)
  found actually predicts performance — none of which requires a named framework.
- **A framework is scaffolding, not the building.** SAFe or LeSS can be a reasonable
  starting structure for an org with no shared practice, *if* it is treated as a temporary
  aid to be shed as the org matures — not as a permanent identity.
- **Copy context, not artifacts.** The Spotify lesson is that structures work because of the
  culture and constraints around them; lifting the org chart without the context reliably
  fails.
- **Watch for inversion.** The moment the process is serving itself — measured by compliance
  rather than by outcomes and [working software](outcomes-over-output.md) — it has become
  the thing agile was created to escape.

## Why it matters

Scaling agile is where the movement's ideals meet organizational reality, and where its
worst distortions live. Understanding both the frameworks and their critiques is what lets a
team adopt what helps, refuse what is theater, and keep the small handful of principles that
actually carry the value — feedback, small steps, and respect for the people doing the work.

## References

- [Agile and the Agile Manifesto](agile-and-the-agile-manifesto.md)
- [Scrum](scrum.md)
- [Team Topologies](../devops-sre/team-topologies.md)
