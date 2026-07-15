---
type: Concept
title: Margins, Tolerances, and Uncertainty
tags: [engineering, tolerances, safety-factor, uncertainty, error-budget, measurement]
timestamp: 2026-07-14
---

# Margins, Tolerances, and Uncertainty

Engineering happens in a world that is never exact. Materials vary between batches, parts
are made to imperfect dimensions, loads are not known precisely, and every measurement
carries error. **Margins, tolerances, and uncertainty** are the family of ideas engineers
use to design things that work anyway — not by pretending the variation is absent, but by
budgeting for it explicitly. Where [modeling and abstraction](modeling-and-abstraction.md)
produces a nominal prediction, this discipline surrounds that prediction with the band of
values that could actually occur and makes the design robust across the whole band.

## Margins and safety factors

A **safety factor** (or factor of safety) is the ratio of a component's capacity to the
load it is expected to bear:

$$\text{FoS} = \frac{\text{capacity (strength)}}{\text{demand (load)}}.$$

A structure designed with FoS = 2 can carry twice its rated load before failing. The margin
absorbs everything the model did not capture: material scatter, degradation over time,
overloads, and plain ignorance. Codes prescribe factors by domain — modest for well-known
static steel structures, large for brittle or life-critical parts, larger still where the
loads themselves are poorly known. A **margin of safety**, MS = FoS − 1, expresses the same
idea as the fractional headroom remaining. The choice is a judgment call, a canonical
engineering heuristic (see [koen-discussion-of-the-method.md](koen-discussion-of-the-method.md)):
too small courts failure, too large wastes material and money. Petroski's central lesson
is that these margins exist precisely because
[failure](failure-analysis-and-root-cause.md) is the teacher — factors of safety encode
the accumulated memory of past collapses
([petroski-to-engineer-is-human.md](petroski-to-engineer-is-human.md)).

## Tolerances and tolerance stack-up

A **tolerance** is the allowed deviation of a dimension from its nominal value — a shaft
specified as 10.00 ± 0.02 mm. No feature can be made perfectly, so every dimension on a
drawing carries a tolerance, and the tolerance is a contract about how much variation the
design can absorb while still functioning (and, in an assembly, still fitting). Tighter
tolerances cost more to manufacture and inspect, so an engineer sets each one as loose as
the function allows — no looser, no tighter.

**Tolerance stack-up** is what happens when toleranced parts are assembled in series. The
individual deviations accumulate, and the worst case can be larger than any single
tolerance suggests. Two methods bound the result:

| Method | How the tolerances combine | Assumes | Result |
| --- | --- | --- | --- |
| **Worst-case** | arithmetic sum: $T = \sum_i t_i$ | every part simultaneously at its extreme | conservative, wide, guarantees fit |
| **Statistical (RSS)** | root-sum-square: $T = \sqrt{\sum_i t_i^2}$ | deviations independent and roughly normal | tighter band, small accepted defect rate |

Worst-case never fails but over-designs; statistical stack-up exploits the fact that
independent errors rarely all point the same way, trading a small, quantified defect rate
for looser, cheaper parts. Choosing between them is a risk decision.

## Uncertainty and error budgets

Uncertainty comes in two flavors that must not be conflated: **random** error (scatter that
averages out with repeated measurement) and **systematic** error (a fixed bias — a
miscalibrated instrument — that repetition does *not* remove). Random error is described by
a standard deviation and analyzed with the tools of
[estimation](../statistics/estimation.md); systematic error is hunted down by calibration
against a known standard.

When a result is *computed* from several uncertain inputs, the uncertainties must be
combined — **propagation of uncertainty**. For a function *y = f(x₁, …, xₙ)* with
independent inputs, the first-order rule is

$$\sigma_y^2 \approx \sum_i \left(\frac{\partial f}{\partial x_i}\right)^2 \sigma_{x_i}^2,$$

so each input's contribution is weighted by how sensitively the output depends on it. An
**error budget** turns this around: given a target uncertainty for the whole system, it
allocates an allowable uncertainty to each component, revealing which few contributors
dominate and therefore deserve the precision (and the money). Error budgets are how
precision instruments, telescopes, and semiconductor tools are actually designed.

## Physical-world calibration

Unlike a pure mathematical result, a physical measurement is only as trustworthy as its
**calibration** — its comparison against a traceable standard. Instruments drift; a scale
reads high, a thermocouple ages. Calibration ties a reading back through a chain of
standards to a defined reference, and it is the mechanism that converts a raw number into a
*measurement with a stated uncertainty*. No margin analysis is meaningful if the numbers
feeding it are uncalibrated. When variation is deliberately introduced and studied to learn
its effect, the design of those trials is itself a discipline — see
[../statistics/experimental-design-and-ab-testing.md](../statistics/experimental-design-and-ab-testing.md).

## Why it matters

Margins, tolerances, and uncertainty are the connective tissue between an idealized model
and a manufacturable, dependable artifact. They translate "the model says it will hold"
into "it will hold across the full range of conditions it will actually see." Set them too
tight and the thing is fragile or unbuildable; set them too loose and it is heavy, costly,
and wasteful. This budgeting of variation is the quantitative backbone of
[reliability engineering](reliability-engineering.md) — a reliability figure is ultimately
a statement about how often the demand exceeds the capacity once all the uncertainty is
accounted for.

## References

- [Estimation](../statistics/estimation.md) — quantifying random error and standard error.
- [../statistics/experimental-design-and-ab-testing.md](../statistics/experimental-design-and-ab-testing.md) — studying the effect of controlled variation.
- [Modeling and Abstraction](modeling-and-abstraction.md) — the nominal prediction that margins wrap around.
- [Reliability Engineering](reliability-engineering.md) — margins expressed as failure probabilities over time.
- [Petroski, *To Engineer Is Human*](petroski-to-engineer-is-human.md) — safety factors as the codified memory of past failures.
- [Koen, *Discussion of the Method*](koen-discussion-of-the-method.md) — margins and tolerances as engineering heuristics.
