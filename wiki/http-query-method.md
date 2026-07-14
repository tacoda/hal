---
type: Image
title: "HTTP QUERY Method: A New Verb"
tags: [http, api-design, rest, query, idempotency, ietf]
timestamp: 2026-07-14
---

# HTTP QUERY Method: A New Verb

A comparison card for the proposed **QUERY** HTTP method (IETF HTTP QUERY Method draft):
QUERY is **safe and idempotent like GET**, but **carries a request body like POST**.

| Property | GET | QUERY | POST |
|---|---|---|---|
| Safe | ✅ | ✅ | ❌ (by convention only) |
| Idempotent | ✅ | ✅ | ❌ (by convention only) |
| Request body | ❌ | ✅ | ✅ |
| Cacheable | ✅ | ✅ | limited |

The gap it fills: complex reads whose parameters are too large or structured for a URL
(so GET doesn't fit), but which shouldn't lose GET's safety/idempotency/cacheability by
being forced onto POST.

## Cross-links

Fits the API-design / idempotency topics in
[System Design Master Tree](system-design-master-tree.md).
