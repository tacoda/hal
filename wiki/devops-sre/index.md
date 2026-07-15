---
type: Index
title: DevOps & SRE
timestamp: 2026-07-14
---

# DevOps & SRE

Delivery & operations — DevOps, SRE, CD, chaos, IaC, team topologies, observability.

- [Accelerate](accelerate.md) — the science behind the four DORA metrics: deploy frequency, lead time, change-fail rate, MTTR
- [Blameless PostMortems and a Just Culture](blameless-post-mortems.md) — Allspaw on why "second stories," not blame, make systems safer
- [Chaos Engineering](chaos-engineering.md) — Rosenthal & Jones: experiment on a system to build confidence in its resilience — steady-state hypothesis, real-world events, minimize blast radius, game days
- [Continuous Delivery](continuous-delivery.md) — Humble & Farley: keep every commit releasable via an automated deployment pipeline; build the binary once
- [The DevOps Handbook](devops-handbook.md) — Kim/Humble/Debois/Willis: the Three Ways (flow, feedback, continual learning) via pipelines, telemetry, generative culture
- [Effective DevOps](effective-devops.md) — DevOps as culture not tooling: the four pillars (collaboration, affinity, tooling, scaling); not a title/team/product
- [Infrastructure as Code](infrastructure-as-code.md) — Kief Morris: infra config as versioned code — immutability, idempotence, small changes, and IaC patterns/anti-patterns
- [O11ycast — The Observability Podcast](o11ycast-podcast.md) — Honeycomb-hosted observability podcast
- [Observability Engineering](observability-engineering.md) — Majors/Fong-Jones/Miranda: unknown-unknowns vs the three-pillars critique; wide structured events, high cardinality, tracing, SLOs, testing in production
- [The Phoenix Project](phoenix-project.md) — Gene Kim: DevOps as a business novel; the Three Ways, four types of work, the Theory-of-Constraints lineage
- [Site Reliability Engineering (SRE Book + Workbook)](site-reliability-engineering.md) — Google's SLI/SLO discipline, error budgets, toil elimination, sustainable on-call
- [Team Topologies](team-topologies.md) — Skelton & Pais: four team types, three interaction modes, Conway's Law + the inverse maneuver, cognitive load, platform-as-a-product
- [Docker: Container Conventions & Patterns](docker.md) — images as immutable artifacts, layer-cache-ordered Dockerfiles, multi-stage/distroless, one concern per container, config from the environment
- [Kubernetes: Orchestration Conventions & Patterns](kubernetes.md) — declarative desired state via the reconciliation loop, pod/deployment/service, labels/selectors, probes & limits, operators, GitOps
- [GitHub as the SDLC Control Plane](github.md) — PR review, GitHub Flow, branch protection, Actions (CI/CD, OIDC), releases, environments/deploys, Dependabot/CodeQL/CODEOWNERS
- [Software Distribution and Publishing](software-distribution.md) — publishing across RubyGems/PyPI/npm, Homebrew, and curl|sh; SemVer/changelogs/signing, and the integrity tradeoff of piped installers
