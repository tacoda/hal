---
type: Reference
title: The C Programming Language (K&R)
tags: [computer-science, c, programming-languages, systems-programming, foundations, unix]
timestamp: 2026-07-14
source: https://www.pearson.com/en-us/subject-catalog/p/c-programming-language-the/P200000000368
---

# The C Programming Language (K&R)

By Brian W. Kernighan and Dennis M. Ritchie (Prentice Hall; 2nd ed. 1988, covering
ANSI C). Universally abbreviated **K&R**, this is the definitive book on the C
language — written by the language's own designer (Ritchie) and his colleague, it is
both the original tutorial and, for a generation, the de facto specification before the
ISO standard existed. At roughly 270 pages it is famously *terse*: it teaches the whole
language, its library, and the taste for spare, direct code in less space than most
single chapters of a modern language reference. It is the anchor text for
[c-language.md](c-language.md).

## What it covers

The book is organized as a working programmer's tour, not a formal grammar. It opens
with the "hello, world" program — the phrase K&R put into the culture — and proceeds
through the language in the order you would actually build up competence:

- **Types, operators, expressions** and control flow — the imperative core.
- **Functions and program structure**, including the crucial rules about scope,
  storage class (`static`, `extern`, `auto`, `register`), and separate compilation.
- **Pointers and arrays** — the chapter the book is most known for. C's identification
  of pointers with array access, pointer arithmetic, and pointers to functions are
  developed with a directness that is still the clearest treatment in print.
- **Structures**, unions, `typedef`, and self-referential data (linked lists, trees).
- **Input/output** and the **standard library** as a thin, portable interface over the
  operating system — the reference appendix documents the library that became the model
  for the ISO C standard library.
- The **UNIX system interface** chapter, tying the language directly to the OS whose
  companion it is — see [../linux/unix-philosophy.md](../linux/unix-philosophy.md).

## Its place in history

C and the book grew up alongside **UNIX** at Bell Labs in the early 1970s: Ritchie
created C to rewrite the UNIX kernel in a portable high-level language, and the two have
been inseparable ever since. The first edition (1978) defined "K&R C" — the informal
standard the whole industry coded to for a decade. The second edition (1988) was revised
to match the then-new **ANSI C (C89)** standard, adding function prototypes and aligning
the library. That the language's specification and its best tutorial were for years the
*same slim book* is a large part of why C spread so fast and stayed so small.

Beyond C itself, K&R set a durable style — the "K&R style" of brace placement, short
functions, and unadorned prose that lets the code speak. The book pairs naturally with
[compilers-and-interpreters.md](compilers-and-interpreters.md): it shows the language a
C compiler must accept, while the compiler texts show how that acceptance is
implemented.

## Why it belongs in this wiki

K&R is where the systems *lingua franca* was first written down by the person who
designed it. Understanding what nearly every other language eventually calls into — the
C ABI, `libc`, the syscall layer — starts with the model this book teaches. It is the
primary reference behind the [c-language.md](c-language.md) concept note.

## References

- [The C Programming Language, 2nd ed. — Kernighan & Ritchie (Pearson/Prentice Hall)](https://www.pearson.com/en-us/subject-catalog/p/c-programming-language-the/P200000000368)
