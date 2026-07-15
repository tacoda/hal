---
type: Index
title: Languages & Frameworks
tags: [languages, frameworks, conventions, patterns, index]
timestamp: 2026-07-14
---

# Languages & Frameworks

The **standards, patterns, conventions, idioms, and methodology** of the languages and
frameworks I work in — *not* API/reference documentation (that lives in an MCP docs
server). Each note captures the "way" of the tool: its philosophy, idiomatic style,
project conventions, common patterns and anti-patterns. These are `Concept` notes; each
`## References` points to the canonical style guide / doctrine, not the API.

Cross-links follow the real dependencies: each framework links to its language, peers link
to each other, and everything ties back to the craft/architecture canon in
[software engineering](../software-engineering/index.md),
[software architecture](../software-architecture/index.md), and
[web & frontend](../web-frontend/index.md).

## Languages

- [Ruby](ruby.md) — POLS, everything-is-an-object, blocks & duck typing, RuboCop style, DSL culture
- [Python](python.md) — the Zen (PEP 20), PEP 8, "one obvious way," pythonic idioms, hints + duck typing
- [PHP](php.md) — PSR standards, Composer autoloading, modern typed PHP
- [Go](go.md) — simplicity, gofmt, explicit errors, implicit interfaces, "share memory by communicating"
- [JavaScript](javascript.md) — the good-parts subset, ESM, async/await, functional array methods
- [TypeScript](typescript.md) — types as design, strict mode, structural typing, `unknown` over `any`

## Backend web frameworks

- [Rails](rails.md) — convention over configuration, the Rails Doctrine, MVC + Active Record *(Ruby)*
- [Hanami](hanami.md) — explicitness over magic, slices, DI container, hexagonal core *(Ruby)*
- [Django](django.md) — batteries-included, the design philosophies, apps, ORM/migrations, MTV *(Python)*
- [FastAPI](fastapi.md) — type-hints-as-contract, Pydantic models, dependency injection, async-first *(Python)*
- [Flask](flask.md) — the "micro" philosophy, application factory, blueprints, WSGI *(Python)*
- [Laravel](laravel.md) — developer-experience elegance, Eloquent, artisan, the container *(PHP)*
- [Gin](gin.md) — idiomatic-Go minimalism, middleware chains, router groups *(Go)*
- [Echo](echo.md) — high-performance minimalist Go web framework, central error handler *(Go)*

## Frontend

- [React](react.md) — "thinking in React," one-way data flow, hooks conventions, state colocation
- [Vue](vue.md) — the priority-tiered style guide, single-file components, Composition vs Options API
- [Svelte](svelte.md) — compiler-not-runtime, "write less code," reactivity via assignment/runes
- [Next.js](nextjs.md) — file-based App Router, React Server Components, rendering strategies *(React)*
- [htmx](htmx.md) — hypermedia as the engine of application state; "you probably don't need a SPA"
- [Hotwire](hotwire.md) — HTML-over-the-wire via Turbo + Stimulus; the anti-SPA approach *(Rails)*

## CLI & TUI

- [Typer](typer.md) — type hints define the CLI; the FastAPI philosophy for command-line apps *(Python)*
- [Textual](textual.md) — Python TUI: App/Widget/Screen, TCSS styling, reactive attributes, messages
- [Cobra](cobra.md) — Go's de-facto CLI framework: commands-as-a-tree, flags, `cobra-cli` layout *(Go)*
- [Bubble Tea](bubbletea.md) — Go TUI on The Elm Architecture: Model–Update–View, Msg/Cmd *(Go)*

## Agent frameworks

- [LangChain](langchain.md) — composition via LCEL/Runnables, chains vs agents, when the abstraction earns its keep *(Python)*
- [LangGraph patterns](langgraph-patterns.md) — the agent loop as an explicit typed state graph; reducers, checkpointing, interrupts *(Python)*

## Related fields

[Web & Frontend](../web-frontend/index.md) (the frontend book canon),
[Software Engineering](../software-engineering/index.md) (craft & testing),
[Software Architecture](../software-architecture/index.md) (DDD, hexagonal, microservices),
[Agentic Coding](../agentic-coding/index.md) and [AI Platform](../ai-platform/index.md)
(the LangChain/LangGraph ecosystem).
