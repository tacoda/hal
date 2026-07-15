---
type: Concept
title: TypeScript Conventions and Type Design
tags: [typescript, ts, types, conventions, structural-typing, generics]
timestamp: 2026-07-14
---

# TypeScript Conventions and Type Design

TypeScript is JavaScript with a static, structural type system layered on top. Its
philosophy is pragmatic rather than purist: it is a **superset** of
[javascript](javascript.md), it never changes runtime behavior (types are erased at
compile time), and it prefers to be *useful* over *sound* — deliberately accepting a few
unsound escape hatches in exchange for describing the messy reality of real JS code. The
convention that matters most is a mindset: **treat types as a design tool, not as
annotations bolted on afterward.** Well-designed types make illegal states unrepresentable
and turn whole classes of bug into compile errors.

## Structural typing

TypeScript uses **structural typing** ("duck typing"): compatibility is decided by an
object's *shape*, not by declared inheritance. If a value has all the members a type
requires, it is assignable to that type — no `implements` needed. This mirrors the implicit
interfaces of [go](go.md) and it means you describe the data you actually have, then let the
compiler check that it fits where it is used.

## Strictness earns its keep

The single highest-leverage convention is **enabling `strict` mode** (in particular
`strictNullChecks` and `noImplicitAny`). Without it, `null`/`undefined` slip into every
type and `any` spreads silently, so most of the value of the type system evaporates. With
it, the compiler forces you to handle absence explicitly — the TS analogue of Go's explicit
error handling.

## Let inference work; annotate at boundaries

Idiomatic TS **does not annotate everything**. Let inference derive local types from
initializers and return values; add explicit annotations where they carry design intent and
where inference cannot help:

- **Function parameters and public/exported API boundaries** — annotate, so the contract is
  stated and stable.
- **Local variables with an obvious initializer** — leave inferred; annotations there are
  noise.

The rule of thumb: annotate the edges, infer the interior.

## `unknown` over `any`, and narrowing

`any` disables the type checker for a value and everything it touches — it is the crack
through which bugs re-enter. The convention is **`unknown` at untyped boundaries** (JSON,
`catch` clauses, external data), then **narrow** it before use. Narrowing is central to
idiomatic TS: `typeof`, `instanceof`, `in`, equality checks, and user-defined type
guards (`x is Foo`) progressively refine a broad type to a specific one, and the compiler
follows the control flow.

```ts
function parse(input: unknown): number {
  if (typeof input === "number") return input;   // narrowed to number
  if (typeof input === "string") return Number(input);
  throw new Error("unsupported input");
}
```

## Discriminated unions model states

The idiomatic way to model "one of several shapes" is a **discriminated (tagged) union** —
a shared literal `kind`/`type` field the compiler switches on. Combined with an exhaustive
`switch` and a `never` default case, the compiler guarantees every variant is handled and
flags any new one you forget:

```ts
type Result =
  | { kind: "ok"; value: number }
  | { kind: "error"; message: string };
```

This is how TS makes illegal states unrepresentable — the reason to reach for types as a
design tool in the first place.

## Generics for reusable, type-safe abstractions

Generics let functions and types operate over any type while preserving the relationships
between inputs and outputs (`function identity<T>(x: T): T`). The convention is to use them
where they capture a real relationship and to **avoid over-parameterizing** — a type
variable that appears only once is usually unnecessary. `interface` vs `type`: prefer
`interface` for object shapes that may be extended or merged, `type` for unions,
intersections, tuples, and mapped/conditional types.

## Types vs. tests

Types and tests are complementary. Types prove **structural** properties for free at every
call site — a value has the right shape, a variant is handled — while tests prove
**behavioral** properties. Strong types shrink the space a test suite must cover, which is
why type-first design pays off in changeability.

## Migrating from JavaScript

The pragmatic migration path, enabled by the superset design:

1. Rename `.js` → `.ts` (or add `allowJs`), compiling with loose settings first.
2. Replace implicit `any` with real types file by file, starting at the boundaries.
3. Turn on `strict` incrementally (`noImplicitAny`, then `strictNullChecks`).
4. Replace `any` escape hatches with `unknown` + narrowing as confidence grows.

## Related

TypeScript is the type layer over [javascript](javascript.md); it is the default in modern
[react](react.md), [vue](vue.md), and [svelte](svelte.md) codebases, where component props,
state, and events are all typed.

## References

- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [TypeScript Do's and Don'ts](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html)
- [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
- [ts.dev Style Guide](https://ts.dev/style/)
