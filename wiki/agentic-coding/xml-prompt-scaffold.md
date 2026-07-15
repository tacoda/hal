---
type: Image
title: XML Prompt Scaffold for Coding Agents
tags: [prompting, coding-agents, xml, claude, harness]
timestamp: 2026-07-14
---

# XML Prompt Scaffold for Coding Agents

A structured prompt template using XML tags to fence each concern when directing a coding
agent on a production codebase.

```xml
<context>
  This is a brownfield production codebase. This project does xyz.
</context>

<tasks>
  <task>This is task1</task>
  <task>This is task2</task>
</tasks>

<rules>
  <rule>Read relevant files before changing code.</rule>
  <rule>Do not speculate about code you have not opened.</rule>
  <rule>Implement the actual general logic.</rule>
  <rule>Do not hard code values to satisfy tests.</rule>
  <rule>Make the smallest safe change.</rule>
  <rule>Do not refactor unrelated code.</rule>
  <rule>Preserve backward compatibility.</rule>
  <rule>don't add libraries without asking me</rule>
</rules>

<tests>
  <test>Add or update tests for happy path</test>
  <test>test edge cases</test>
  <test>test invalid input</test>
</tests>

<review>
  Review for correctness, security, concurrency, performance,
  production readiness and rollback safety.
</review>

<output>
  Explain the diff like a PR author. Show me the diff. don't commit
</output>
```

The value is the separation: context, tasks, rules, tests, review criteria, and output
format each get their own fenced block instead of one run-on paragraph.

## Cross-links

The per-turn instruction discipline that the context/verification layers of
[Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md) enforce structurally; "don't
hard code values to satisfy tests" is exactly the false-success failure its verifier
catches.
