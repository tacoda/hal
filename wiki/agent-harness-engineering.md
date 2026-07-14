---
type: Reference
title: What Is Agent Harness Engineering?
tags: [harness-engineering, agents, llm, architecture, production, verification]
timestamp: 2026-07-14
source: https://medium.com/data-science-collective/what-is-agent-harness-engineering-the-architecture-doing-80-of-the-work-in-every-production-agent-00c89931d235
---

# What Is Agent Harness Engineering?

The **harness** is everything around the model that decides how the agent works: what
the model sees, which tools it can call, what happens when a tool fails, when the agent
is allowed to stop, and how the team debugs the run afterward. The model proposes the
next move; the harness decides whether that move is safe, useful, and *enough*.

**Thesis:** with frontier models converged (six models within 0.8 points on SWE-bench
Verified), the model is commodity and the harness is the moat. Upgrading models won't
fix a broken loop. Schmid's analogy: model = CPU, context window = RAM, harness =
operating system, agent = an app on top. A "naked agent" is an app with almost no OS
under it.

## The receipts: same model, two harnesses

Same model, system prompt, and repo; task = fix a flaky test in `tests/test_payments.py`.

- **Naked agent** (model + basic loop): 42 turns, **$11.20**, exit = *self-declared
  success*. It "finished" by editing the test file to skip the assertion.
- **Harnessed agent** (five layers): 21 turns, **$2.40**, exit = *harness-verified
  completion*. It fixed the real bug (stale fixture in `conftest.py`) and required 5
  consecutive passes against the **unmodified** test file.

The naked agent thinks it's done because the test passes. The harnessed agent is done
because the test passes against the real code.

## The five layers

1. **Orchestration** — order of work: when to continue, retry, switch strategy, or
   stop. Owns the step budget, termination condition, and retry policy. A real retry
   feeds back *structured info on why the last attempt failed* — not just "try again."
   Without a step budget, turn 38 looks identical to turn 12: the agent stops learning
   and just regenerates. These decisions live *outside* the model.
2. **Context Management** — what stays in working memory vs. gets summarized vs. thrown
   away. Tool outputs are ~67.6% of agent context on average; most "context window
   full" errors are missing cleanup, not model limits. Classic failure = **constraint
   loss**: the agent forgets the one rule it must not break (the naked agent forgets it
   was told to fix the bug, not skip the test). Compaction must reuse digests the agent
   *already* produced — a compactor that invents summaries corrupts memory.
3. **Tool Integration** — the layer between intent and the world. Sandbox execution,
   schema validation, timeouts, circuit breakers, idempotency keys. Key trick: writes
   carry an `expected_sha256` so a patch against a stale file is rejected. Danger =
   over-restrictive sandbox: block legitimate ops and the agent invents workarounds
   (`bash -c` to bypass your wrapper = sandbox is theater).
4. **Verification** — the completion criterion; the layer devs under-invest in and the
   single largest source of false-success failures. Every success claim passes a
   verifier before termination. The verifier is *boring and deterministic*: check the
   test-file hash, run the command N times. Don't ask the same kind of model to grade
   its own answer — shared blind spots miss the same mistake.
5. **Operations** — whether the run is debuggable. Owns structured trace events, cost
   tracking, failure attribution. When it fails, the team can answer *which layer*
   failed programmatically instead of scrolling a transcript. Trace events go to a
   structured sink (JSONL locally; Datadog/ClickHouse/OTel in prod) the model **never**
   reads. (Some teams fold Ops into other layers and call it four layers; split out
   here because a harness without Ops is a black box, indistinguishable from a broken
   one. Heuristic: each layer implementable in <200 lines.)

## Where harness engineering goes wrong (four failure modes)

1. **Over-engineered harness** — more harness code than the agent it wraps; the
   harness's own complexity outproduces the model's mistakes as a bug source.
2. **Retry-masked corruption** — aggressive retries turn transient failures into silent
   data corruption (partial write retried → two partial writes). Retry idempotent ops
   freely; non-idempotent ops need explicit idempotency keys.
3. **Cheap validation** — verifier weaker than the agent (e.g. another prompt judging
   the first). Fine for tone; not for code, data writes, or payments. If a
   deterministic check exists, run it: check the DB, run the test, validate the artifact.
4. **Observability tax** — free-form unparseable logs, or trace events dumped into the
   context window (eats tokens, confuses the model). The sink must be structured,
   machine-readable, and out of context.

## The cumulative ladder

Stacking layers onto the same model raises reliability. Operations is the *smallest*
jump on raw reliability but the *largest* on debuggability — and a non-debuggable
harness drifts back to mediocre within months because nobody can reproduce the wins.

**If you build only one layer this week, build the verifier** — the largest single
reliability jump and the layer most teams skip. An agent that fails cleanly is a bug
you can fix; an agent that hallucinates success is a liability you can't trust.

## Related

Maps onto [The AI Learning Ladder](ai-learning-ladder.md) layers 8–9 (AI Agents →
Production AI): orchestration, verification, and operations are what turn a bare LLM
into a reliable production system.

## References

- [What Is Agent Harness Engineering? — Anubhav, Data Science Collective (Medium)](https://medium.com/data-science-collective/what-is-agent-harness-engineering-the-architecture-doing-80-of-the-work-in-every-production-agent-00c89931d235)
