---
type: Concept
title: Flask Conventions & Philosophy
tags: [flask, python, web-frameworks, microframework, wsgi, blueprints]
timestamp: 2026-07-14
---

# Flask Conventions & Philosophy

Flask is a Python **microframework**: a small, sharp core (routing + request/response,
built on the Werkzeug WSGI toolkit and the Jinja2 template engine) that deliberately
leaves most decisions to you. Its philosophy is **explicit over batteries-included** —
the framework makes as few choices as possible on your behalf, and the choices it does
make are easy to change. It sits at the opposite pole from batteries-included
[Django](django.md), and it differs from [FastAPI](fastapi.md) along a second axis:
Flask is a synchronous **WSGI** framework, where FastAPI is async-first **ASGI**. All
three share the same substrate — see [python.md](python.md).

## What "micro" means

"Micro" does **not** mean minimal capability or one-file apps. It means the *core* stays
small and extensible: Flask ships no database layer, no form validation, no auth — those
are handled by **extensions** (Flask-SQLAlchemy, Flask-WTF, Flask-Login, …) that plug in
as if native. The one opinion Flask holds firmly (Jinja2 templating) is still swappable.
The bargain: Flask can be "everything you need and nothing you don't," at the cost of you
assembling the stack. Contrast Django, which answers all of these questions for you up
front.

## Explicit over implicit

Flask's design decisions repeatedly favor explicitness:

- **The explicit application object.** You create `app = Flask(__name__)` yourself rather
  than importing a magic global `route` decorator. This is deliberate: an implicit app
  would force a single instance, whereas an explicit object lets you create multiple apps
  (crucial for isolated unit tests) and pass the app around as a normal value.
- **No hidden convention scaffolding.** Flask doesn't generate a project skeleton or
  impose an MVC layout. Structure is your responsibility — which is freedom and rope in
  equal measure.

## WSGI and the request lifecycle

Flask is tied to **WSGI**: one central callable receives a request and returns a
response, synchronously. Flask *supports* `async def` view functions, but it does so by
running the coroutine on a separate thread rather than on an event loop — a
compatibility compromise that carries thread overhead and is not the same as a native
ASGI framework. If your workload is I/O-bound and async-heavy, that gap is exactly why
[FastAPI](fastapi.md) exists.

## Application and request context

Because Flask uses **context-local** objects (thread/greenlet locals), you access
`request`, `session`, `g` (a per-request scratchpad), and `current_app` as importable
globals that resolve to the *current* request/app. Two contexts bracket a request:

- **Application context** — active while an app is handling work; backs `current_app`
  and `g`.
- **Request context** — active per request; backs `request` and `session`.

The convention: treat `g` as request-scoped storage (e.g. the DB connection for this
request), not as a general cache. Flask openly acknowledges thread-locals are usually a
questionable idea for large or async apps — it accepts that tradeoff because it targets
traditional, threaded web apps and prizes ergonomics.

```mermaid
flowchart LR
  R[Incoming WSGI request] --> AC[App context pushed<br/>current_app, g]
  AC --> RC[Request context pushed<br/>request, session]
  RC --> V[View function]
  V --> RESP[Response]
  RESP --> POP[Contexts popped / teardown]
```

## The application factory pattern

The idiomatic way to structure a non-trivial Flask app is a **factory function** —
`create_app()` that builds and returns a configured `Flask` instance:

```python
def create_app(config=None):
    app = Flask(__name__)
    app.config.from_object(config or "myapp.config.Default")

    from myapp.models import db
    db.init_app(app)                      # bind extension to THIS app

    from myapp.blog import bp as blog_bp
    app.register_blueprint(blog_bp)       # register features
    return app
```

Why it's the convention:

- **No import-time app** — nothing runs at module load, so you can create a fresh,
  minimally-configured app per test (the explicit-app payoff realized).
- **Multiple configurations** — dev, test, prod configs produce different apps from the
  same factory.
- **Extensions bind late.** Instantiate extensions unbound at module level
  (`db = SQLAlchemy()`), then call `db.init_app(app)` inside the factory. Storing no
  app-specific state on the extension lets one extension object serve multiple apps.

## Blueprints for structure

**Blueprints** are Flask's unit of modularity: a blueprint groups routes, templates, and
static files for a feature, registered onto the app (optionally under a URL prefix). They
give large apps structure without a mandated layout — the convention is one blueprint per
feature/domain, registered in the factory. Blueprints are how a Flask app scales from one
file to a package while keeping the "explicit, assemble-it-yourself" character.

## Patterns and anti-patterns

- **Do** use `create_app()` factories and register features as blueprints.
- **Do** instantiate extensions unbound and `init_app()` them in the factory.
- **Do** put request-scoped resources on `g`; tear them down with `teardown` handlers.
- **Don't** create the app (or bind extensions to it) at import time — it breaks testing
  and multi-config setups.
- **Don't** lean on `async def` views expecting event-loop concurrency; reach for
  [FastAPI](fastapi.md) if the app is genuinely async/I/O-bound.
- **Don't** stuff persistent/shared state into `g` — it lives only for one request.

Flask apps are also natural [Twelve-Factor](../distributed-systems/twelve-factor-app.md)
citizens: config comes from the environment (`app.config.from_...`), and the app is a
stateless process behind a WSGI server. Compare the opinionated, batteries-included
alternative in [Django](django.md) and the async ASGI alternative in
[FastAPI](fastapi.md).

## References

- [Design Decisions in Flask](https://flask.palletsprojects.com/en/stable/design/)
- [Application Factories](https://flask.palletsprojects.com/en/stable/patterns/appfactories/)
- [Flask documentation](https://flask.palletsprojects.com/)
