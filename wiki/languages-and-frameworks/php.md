---
type: Concept
title: PHP conventions and philosophy
tags: [php, conventions, psr, composer, style-guide, oop]
timestamp: 2026-07-14
---

# PHP conventions and philosophy

PHP began as a set of templating tools for embedding logic directly in HTML, and its
early culture reflected that: scripts mixed markup, database calls, and business logic
freely, with little shared convention. Modern PHP is a different language in practice.
Since PHP 7 and 8 it has become a strongly-featured, gradually-typed, object-oriented
language, and — just as importantly — the community coalesced around a set of shared
standards (the PSRs) and a single dependency manager (Composer) that gave the ecosystem
the consistency it previously lacked. Idiomatic modern PHP looks far more like Java or
C# than like the inline-template PHP of the 2000s.

## Design philosophy

PHP has no single manifesto like Python's Zen. Its guiding values are pragmatic:

- **Built for the web request lifecycle.** PHP's model is share-nothing: each request
  starts fresh, runs, and tears down. This simplicity (no long-lived shared state to
  reason about) is a large part of why PHP scaled the early web.
- **Gradual modernization.** The language accumulated a reputation for inconsistency
  (mixed function-naming, loose typing). Rather than break everything, modern PHP layers
  in rigor opt-in: strict types, typed properties, enums, readonly, attributes — you
  adopt them incrementally.
- **Convention through community standards.** Where the language stayed permissive, the
  **PHP-FIG** (Framework Interoperability Group) supplied the discipline via the PSR
  recommendations, so libraries from different vendors interoperate.

## The PSR standards

The PHP Standards Recommendations are the backbone of modern PHP convention. The ones
that shape everyday code:

- **PSR-1 — Basic Coding Standard.** Files use `<?php` / `<?=` only, class names in
  `StudlyCaps`, method names in `camelCase`, constants in `UPPER_SNAKE_CASE`, and a file
  should *either* declare symbols *or* cause side effects — not both.
- **PSR-12 — Extended Coding Style** (supersedes the older PSR-2). The formatting rule
  set: 4-space indentation (no tabs), one class per file, braces on their own line for
  classes/methods, visibility declared on every property and method, one blank line
  after the namespace, and so on. Enforced by tools like PHP-CS-Fixer and PHP_CodeSniffer.
- **PSR-4 — Autoloading.** Maps namespaces to directory paths (`App\Http\Controller`
  → `src/Http/Controller.php`), which is what lets Composer autoload classes without
  manual `require` statements. This standard is why the `require`-everything style
  disappeared.

| Kind | Convention | Example |
| --- | --- | --- |
| Classes, interfaces, traits, enums | `StudlyCaps` / `PascalCase` | `UserRepository` |
| Methods, functions, variables | `camelCase` | `findById`, `$userName` |
| Constants | `UPPER_SNAKE_CASE` | `DEFAULT_TIMEOUT` |
| Namespaces | map to directories (PSR-4) | `App\Domain\Order` |
| Indentation | 4 spaces | |

## Composer and autoloading

**Composer** is the standard dependency manager and the single most important tool in
the modern PHP workflow. `composer.json` declares dependencies and PSR-4 namespace
mappings; `composer.lock` pins exact resolved versions; `vendor/autoload.php` provides
class autoloading. Packages are published to Packagist. This ecosystem — a lockfile, a
central registry, and standardized autoloading — is what turned PHP from a folder of
scripts into a modular library ecosystem.

## Modern PHP conventions

Idiomatic modern PHP embraces the type system and structured OO that recent versions
added:

```php
<?php

declare(strict_types=1);   // opt into strict scalar type checking, top of every file

namespace App\Billing;

final class Invoice
{
    public function __construct(
        private readonly Money $total,     // constructor property promotion + readonly
        private InvoiceStatus $status,     // enum-typed
    ) {}

    public function total(): Money         // typed return
    {
        return $this->total;
    }
}
```

- **`declare(strict_types=1);`** at the top of each file to disable loose type coercion.
- **Typed everything** — typed properties, parameter and return types, union types,
  nullable types.
- **Enums, readonly properties, constructor promotion, first-class callable syntax,
  attributes** (`#[Route(...)]`) replace older idioms (class constants for enum-like
  values, doc-comment annotations for metadata).
- **Separation of concerns.** The cultural shift away from templating means logic lives
  in classes; templates (Blade, Twig) handle only presentation.

## Testing conventions

**PHPUnit** is the dominant test framework — xUnit-style test classes with `test*`
methods or `#[Test]` attributes and assertion methods. `Pest` is a newer expressive
wrapper built on top of PHPUnit. Tests conventionally live in a `tests/` directory,
often mirroring the `src/` structure, and are wired up through Composer's autoloader.

## Frameworks

- **[laravel.md](laravel.md)** — the dominant modern PHP framework; expressive,
  convention-driven, batteries-included (ORM/Eloquent, Blade templates, queues, auth),
  and the main reason many developers experience "modern" PHP conventions in practice.

## References

- [PSR-1 — Basic Coding Standard](https://www.php-fig.org/psr/psr-1/)
- [PSR-12 — Extended Coding Style](https://www.php-fig.org/psr/psr-12/)
- [PSR-4 — Autoloading Standard](https://www.php-fig.org/psr/psr-4/)
- [Composer](https://getcomposer.org/)
- [PHPUnit](https://phpunit.de/)
