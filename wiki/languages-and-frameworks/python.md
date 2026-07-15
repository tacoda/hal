---
type: Concept
title: Python conventions and philosophy
tags: [python, conventions, style-guide, idioms, philosophy, pep8, pep20]
timestamp: 2026-07-14
---

# Python conventions and philosophy

Python is a dynamic, multi-paradigm language designed by Guido van Rossum around a
strong opinion about *how code should read*. Its culture prizes clarity, explicitness,
and a shared sense that for most problems there should be one obvious idiomatic way to
do things. "Pythonic" code is not merely correct code — it is code that follows the
community's conventions closely enough that any other Python programmer recognizes it
immediately.

## Design philosophy — the Zen of Python (PEP 20)

The guiding aesthetic is captured in the Zen of Python, printable with `import this`.
Its aphorisms are the north star for API and code design:

- Beautiful is better than ugly; **explicit is better than implicit**.
- Simple is better than complex; complex is better than complicated.
- **Readability counts.**
- Special cases aren't special enough to break the rules.
- Errors should never pass silently (unless explicitly silenced).
- In the face of ambiguity, refuse the temptation to guess.
- **There should be one — and preferably only one — obvious way to do it.**
- Flat is better than nested; sparse is better than dense.

The "one obvious way" principle is what makes Python codebases feel consistent across
teams: the language and community actively discourage having five ways to accomplish the
same thing.

## PEP 8 — the style guide

Python's formatting conventions are codified in PEP 8, the single authoritative style
document, and are near-universally enforced by tooling (Black, Ruff, Flake8, isort).

| Kind | Convention | Example |
| --- | --- | --- |
| Functions, variables, modules | `snake_case` | `parse_config`, `user_id` |
| Classes, exceptions | `PascalCase` | `HttpClient`, `ValueError` |
| Constants | `UPPER_SNAKE_CASE` | `MAX_SIZE` |
| "Internal" names | leading underscore | `_helper`, `_cache` |
| Indentation | **4 spaces**, never tabs | |
| Line length | 79 (PEP 8) / 88 (Black default) | |

Other PEP 8 staples: two blank lines between top-level definitions, imports grouped
(stdlib, third-party, local) and never wildcard, spaces around binary operators, and a
preference for readability over cleverness. The modern default is to stop arguing about
formatting and let an auto-formatter (Black or Ruff) settle it.

## Pythonic idioms

Idiomatic Python leans on a small vocabulary of constructs that the language is built to
reward:

```python
# Comprehensions over manual loops for building collections
evens = [n for n in numbers if n % 2 == 0]
lookup = {u.id: u for u in users}

# Context managers for resource lifecycle (open/close, lock/unlock)
with open(path) as f:
    data = f.read()          # file closed automatically

# EAFP — "Easier to Ask Forgiveness than Permission"
try:
    value = config["key"]
except KeyError:
    value = default          # preferred over checking `if "key" in config`

# Truthiness and iteration
if not items:                # not `if len(items) == 0`
    return
for i, item in enumerate(items):   # not `for i in range(len(items))`
    ...
```

- **EAFP over LBYL.** Python favors trying an operation and catching the exception
  ("easier to ask forgiveness than permission") over defensively checking first ("look
  before you leap"). This suits dynamic typing and avoids race conditions.
- **Duck typing with optional type hints.** Runtime is dynamically typed and relies on
  behavior, not declared types. Since PEP 484, **type hints** (`def f(x: int) -> str:`)
  add gradual, optional static typing checked by tools like `mypy` and `pyright`. Hints
  are documentation and tooling aid; they do not change runtime behavior.
- **Iterators and generators.** `yield`-based generators express lazy sequences
  cleanly; iteration protocols are pervasive.

## Project layout and tooling conventions

- **Virtual environments are the norm.** Each project gets an isolated environment
  (`venv`, `virtualenv`) so dependencies do not leak between projects.
- **Dependency and packaging** has consolidated on `pyproject.toml` as the single
  project manifest. Tools: `pip` for install, `Poetry` or `uv` for lock-file-based
  resolution and packaging, `hatch` for building.
- A typical layout uses a `src/` package directory, tests in `tests/`, and metadata in
  `pyproject.toml`.

## Testing conventions

**`pytest`** is the de facto standard: plain `assert` statements (rich introspection on
failure), function-based tests, and fixtures for setup/teardown via dependency
injection. The stdlib `unittest` (xUnit-style classes) still ships with Python and
appears in legacy code. Test files are named `test_*.py`.

## Frameworks

- **[django.md](django.md)** — batteries-included web framework; opinionated,
  convention-heavy, ORM and admin included.
- **[fastapi.md](fastapi.md)** — modern async API framework built on type hints and
  Pydantic.
- **[typer.md](typer.md)** — type-hint-driven CLI framework (from the FastAPI author).
- **[langchain.md](langchain.md)** and **[langgraph-patterns.md](langgraph-patterns.md)**
  — LLM application frameworks; see also [../ai/index.md](../ai/index.md).

## References

- [PEP 8 — Style Guide for Python Code](https://peps.python.org/pep-0008/)
- [PEP 20 — The Zen of Python](https://peps.python.org/pep-0020/)
- [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)
- [pytest](https://docs.pytest.org/)
- [Poetry](https://python-poetry.org/)
