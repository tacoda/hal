---
type: Concept
title: Ruby conventions and philosophy
tags: [ruby, conventions, style-guide, idioms, philosophy, oop]
timestamp: 2026-07-14
---

# Ruby conventions and philosophy

Ruby is a dynamic, object-oriented language designed by Yukihiro "Matz" Matsumoto
with an explicit optimization target that is unusual among languages: **programmer
happiness**. Where many languages optimize for machine efficiency or for a small,
verifiable core, Ruby optimizes for the pleasure and expressiveness of the person
writing and reading the code. Almost every convention below is downstream of that
choice.

## Design philosophy

- **Principle of Least Surprise (POLS).** Code should behave the way a reasonable
  reader expects. Matz frames this as *his* least surprise — the language is internally
  consistent enough that once you learn a rule, its consequences follow predictably. The
  practical effect is that idiomatic Ruby reads close to prose and rarely needs
  ceremony to express intent.
- **Everything is an object.** There are no primitives sitting outside the object
  model. `1.even?`, `"hi".upcase`, `nil.to_s`, and `Integer.ancestors` all work because
  integers, strings, `nil`, and classes are ordinary objects that respond to messages.
  Even control-flow constructs return values (`x = if cond then a else b end`).
- **Message passing over data access.** You *send messages* to objects rather than
  reach into their fields. This is why Ruby leans on accessors, `method_missing`, and
  `respond_to?` rather than public attributes.
- **Optimize for the reader, then the writer.** Terseness is valued only when it aids
  comprehension. Clever one-liners that obscure intent are discouraged even though the
  language makes them easy.

## Blocks, iterators, and closures

The block is Ruby's signature construct — an anonymous chunk of code passed to a
method. Idiomatic Ruby almost never uses index-based `for` loops; it sends an iteration
message to a collection and hands it a block:

```ruby
names.map { |n| n.capitalize }        # single-line: braces
names.each do |name|                  # multi-line: do...end
  puts greeting_for(name)
end
```

Convention: `{ }` for single-line blocks that return a value, `do...end` for multi-line
blocks run for their side effects. Blocks enable internal iterators (`each`, `map`,
`select`, `reduce`, `each_with_object`), resource management (`File.open(path) { |f| … }`
closes the file for you), and the DSL style below.

## Duck typing

Ruby does not check types; it checks *behavior*. "If it walks like a duck and quacks
like a duck, it's a duck." You do not ask `is this an Array?`; you call the method you
need and rely on the object responding. This favors small, focused interfaces and makes
polymorphism a matter of implementing the right methods rather than sharing a base
class. See the design consequences in
[../software-engineering/practical-object-oriented-design-in-ruby.md](../software-engineering/practical-object-oriented-design-in-ruby.md).

## Naming and formatting conventions

The community has converged on a single widely followed style guide (enforced by the
RuboCop linter), so Ruby codebases look remarkably uniform.

| Kind | Convention | Example |
| --- | --- | --- |
| Methods, variables | `snake_case` | `total_price`, `user_name` |
| Classes, modules | `CamelCase` | `OrderProcessor`, `HTTP` |
| Constants | `SCREAMING_SNAKE_CASE` | `MAX_RETRIES` |
| Files | `snake_case.rb` matching the class | `order_processor.rb` |
| Indentation | two spaces, never tabs | |

Two naming idioms carry semantic weight:

- **Predicate methods end in `?`** and return a boolean-ish value: `empty?`, `valid?`,
  `nil?`. Reads as a question.
- **Bang methods end in `!`** to signal the "dangerous" or surprising variant — usually
  mutating the receiver or raising instead of returning `nil`: `sort` vs `sort!`,
  `save` vs `save!`. The `!` is a warning to the reader, not a language feature.

Other conventions: prefer `unless` over `if !`, use trailing `if`/`unless` modifiers for
short guard clauses (`return unless valid?`), prefer string interpolation `"#{x}"` over
concatenation, and use `&&`/`||` in expressions but `and`/`or` (low precedence) only for
control flow.

## Expressiveness and DSL culture

Ruby's open classes, blocks, `method_missing`, and flexible syntax (optional parens,
symbols, implicit `self`) make it exceptionally good at building **internal DSLs** —
libraries whose API reads like a domain-specific language. RSpec (`expect(x).to eq(3)`),
Rake (`task :build => :compile`), and [rails.md](rails.md)'s routing and migrations are
all Ruby that reads like configuration. This is a defining part of Ruby culture, though
metaprogramming is applied judiciously in application code because it can hurt
traceability.

## Testing conventions

Testing is a deep part of Ruby culture — the community was central to popularizing TDD
and BDD. Two frameworks dominate:

- **Minitest** — lightweight, ships with Ruby, plain assertions or a spec-style DSL.
- **RSpec** — expressive BDD DSL with `describe`/`context`/`it` blocks and readable
  matchers. See [../software-engineering/effective-testing-with-rspec-3.md](../software-engineering/effective-testing-with-rspec-3.md).

Tests live in `spec/` (RSpec) or `test/` (Minitest), mirroring the source layout.

## Ecosystem conventions

- **Gems** are the unit of packaging; `Bundler` and a `Gemfile` pin and resolve
  dependencies per project.
- **`rbenv`/`rvm`/`chruby`** manage Ruby versions; `.ruby-version` pins the interpreter.
- Refactoring toward these idioms — extracting methods, replacing conditionals with
  polymorphism, honoring duck-typed interfaces — is covered in
  [../software-engineering/refactoring-ruby-edition.md](../software-engineering/refactoring-ruby-edition.md).

## Frameworks

- **[rails.md](rails.md)** — the dominant web framework; convention over configuration
  taken to its logical end.
- **[hanami.md](hanami.md)** — a lighter, more explicit alternative emphasizing clear
  boundaries and dependency injection.

## References

- [Ruby Style Guide (community)](https://rubystyle.guide/)
- [RuboCop](https://rubocop.org/)
- [RSpec](https://rspec.info/)
- [Minitest](https://github.com/minitest/minitest)
