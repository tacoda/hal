---
type: Concept
title: Semantics
tags: [linguistics, semantics, meaning, compositionality, distributional-semantics, embeddings]
timestamp: 2026-07-14
---

# Semantics

**Semantics** is the study of meaning in language: what words mean, how the meanings of
words combine into the meanings of sentences, and how those meanings relate to the world.
It takes the structures delivered by [syntax](syntax.md) and asks what they *say*.
Semantics is the *literal, context-free* layer of meaning; the context-dependent layer —
what a speaker *implies* on a particular occasion — belongs to [pragmatics](pragmatics.md).

## Lexical vs sentential semantics

- **Lexical semantics** concerns the meanings of individual words and the relations among
  them: **synonymy** (*couch*/*sofa*), **antonymy** (*hot*/*cold*), **hyponymy** (*rose* is
  a kind of *flower*), **polysemy** (one word, related senses — *bank* as a slope vs the
  river's edge), and **homonymy** (unrelated senses sharing a form — *bank* the institution
  vs the riverbank). These relations form the semantic network of the lexicon.
- **Sentential (compositional) semantics** concerns how word meanings combine into sentence
  meanings.

## Compositionality

The **principle of compositionality** (often credited to Frege) is the cornerstone: the
meaning of a complex expression is determined by the meanings of its parts and the way they
are syntactically combined. This is why you can understand a brand-new sentence — you know
the words and you know the rule for combining them. Meaning is computed *up the syntax
tree*: *red* modifies *ball* to yield *red ball*, the verb combines with its object, and so
on. Compositionality is what links semantics tightly to syntax, and its failures are
informative: **idioms** (*kick the bucket*) mean more than the sum of their parts, which is
exactly why they must be learned as units.

## Truth-conditional / logical semantics

The dominant formal tradition treats the meaning of a declarative sentence as its
**truth conditions** — the conditions under which it would be true. To *know* the meaning of
*"The cat is on the mat"* is to know what the world must be like for it to be true. This
lets meaning be represented in **logic**: predicates, arguments, quantifiers (∀, ∃), and
logical connectives. *"Every dog barked"* becomes ∀x (dog(x) → barked(x)). Formal semantics
(Montague and successors) shows how to compute these logical forms compositionally from
syntactic structure, giving a precise, computable theory of sentence meaning — the approach
[jurafsky-martin-speech-and-language-processing.md](jurafsky-martin-speech-and-language-processing.md)
covers as logical/semantic representation.

## Sense vs reference

A classic distinction (Frege's *Sinn* vs *Bedeutung*): the **reference** of an expression is
the thing in the world it picks out; its **sense** is the *way* it presents that thing.
*"The morning star"* and *"the evening star"* have the **same reference** (the planet Venus)
but **different senses** — which is why *"the morning star is the evening star"* is
informative rather than a trivial *a = a*. Sense-vs-reference is a foundational problem in
the [../philosophy/index.md](../philosophy/index.md) of language and a reminder that meaning
is not just pointing at objects.

## Distributional semantics — the bridge to embeddings

A different tradition abandons truth conditions for *usage*. The **distributional
hypothesis** (Firth: *"You shall know a word by the company it keeps"*; Harris) holds that a
word's meaning is characterized by the contexts it occurs in — words appearing in similar
contexts have similar meanings. *Dog* and *cat* share neighbors (*pet*, *feed*, *vet*),
so they are semantically close.

This is the direct ancestor of
[../ai/representation-learning-and-embeddings.md](../ai/representation-learning-and-embeddings.md).
Word embeddings (word2vec, GloVe) operationalize the hypothesis exactly: train a model to
predict a word from its context and the learned vectors place distributionally similar words
near each other, yielding a geometry where cosine distance approximates semantic similarity
and analogies fall out as vector arithmetic (*king − man + woman ≈ queen*). Contextual
embeddings in [../ai/transformers-and-attention.md](../ai/transformers-and-attention.md) and
[../ai/large-language-models.md](../ai/large-language-models.md) extend this to *token-in-
context* vectors, which is how such models disambiguate polysemy — the vector for *bank* in
*"river bank"* differs from *bank* in *"bank loan"*.

The catch, and it is a deep one: distributional semantics captures **sense-like similarity
from text alone but never touches reference**. A model can know *dog* patterns like *cat*
without ever having connected either word to an actual animal — the **symbol grounding
problem**. This is the semantic core of the debate over whether LLMs "understand": they have
rich distributional sense but arguably no reference, no truth conditions anchored in the
world. That tension runs straight back to sense-vs-reference and into
[../philosophy/index.md](../philosophy/index.md).

## Why it matters

Semantics is the payoff of the whole linguistic stack — [phonetics-and-phonology](phonetics-and-phonology.md)
and [morphology](morphology.md) build the words, [syntax](syntax.md) structures them, and
semantics extracts what they mean. It feeds [pragmatics](pragmatics.md) (literal meaning is
the input to inferring speaker intent) and
[psycholinguistics](psycholinguistics.md) (how meaning is accessed in real time), and it is
the level where the promise and the limits of statistical language models are argued out.

## References

- [fromkin-introduction-to-language.md](fromkin-introduction-to-language.md)
- [jurafsky-martin-speech-and-language-processing.md](jurafsky-martin-speech-and-language-processing.md)
- [saussure-course-in-general-linguistics.md](saussure-course-in-general-linguistics.md)
