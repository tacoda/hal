---
type: Reference
title: Measuring the ROI of AI Code Assistants
tags: [ai-assisted-development, roi, metrics, measurement, cost, control-group, org]
timestamp: 2026-07-14
source: https://jellyfish.co/library/ai-in-software-development/measuring-roi-of-code-assistants/
---

# Measuring the ROI of AI Code Assistants

Jellyfish's practitioner guide to putting a defensible number on AI coding tools.
Two load-bearing ideas: the **true cost is 2–3× the license**, and the only
credible attribution method is a **control group.**

## The full cost stack (~2–3× subscription)

License fees are the smallest part. Jellyfish's breakdown for a mid-sized team:

| Layer | Includes | Example first-year |
| --- | --- | --- |
| Licenses | Copilot/Cursor, $20–50/dev/mo | $12k–30k |
| Usage fees | API calls, tokens, overages | $6k–36k |
| Training | 4–8 hrs/dev @ $75/hr | $15k–30k |
| Adoption dip | 10–20% drop for 1–2 months | $30k–120k |
| Infrastructure | CI/CD, security config | $6k–12k |
| Tool mgmt + sprawl | licensing, vendor, shadow IT | $14k–33k |
| Compliance | reviews, audits | $6k–12k |

A **50-developer team spends ~$150k–180k in year one — roughly 3× license cost
alone.** Year two drops to ~$70k–90k as one-time setup falls away. Rushed adoption,
expensive tools, and weak governance land you at the high end. This is the
quantified version of the cost stack in [calculating ROI](calculating-roi.md) and
sits alongside [cost management](cost-management.md).

## The methodology that survives scrutiny: control groups

Jellyfish's own Copilot study compared **133 users to 750 non-users at the same
firms** to attribute cycle-time changes to AI rather than to reorgs, new hires, or
easier projects. Their rules for a valid control group:

- Split similar teams; match on **project complexity, tech stack, and seniority**.
- Track the same metrics (cycle time, bug rates, deploy frequency) for both.
- **Rotate** which teams get AI after each period to validate.
- Keep control groups large enough to matter (20–30+ devs).
- Watch for the **Hawthorne effect** — teams improve just from being observed.
- Don't stack the AI group with seniors, cherry-pick timeframes, or let the control
  group use AI "just a little."

## Why it matters

Most teams "measure the wrong things with the wrong tools." Without a control group
every comparison is confounded; without the full cost stack every ROI is inflated.
The discipline mirrors [calculating ROI](calculating-roi.md): net outcomes by task
class, team-level not individual, quantitative paired with qualitative.

## Related

- [Calculating ROI](calculating-roi.md) — the general pattern; this is the how-to.
- [Cost Management](cost-management.md) — controlling the stack this note prices.
- [Rethinking Performance](rethinking-performance.md) — why team-level beats individual.

## References
- [How to Measure the ROI of AI Code Assistants — Jellyfish](https://jellyfish.co/library/ai-in-software-development/measuring-roi-of-code-assistants/)
