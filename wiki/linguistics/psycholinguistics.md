---
type: Concept
title: Psycholinguistics
tags: [linguistics, psycholinguistics, parsing, mental-lexicon, garden-path, priming, comprehension, production]
timestamp: 2026-07-14
---

# Psycholinguistics

Psycholinguistics studies the mental processes and representations that let people
comprehend and produce language in real time. Where much of theoretical linguistics
describes the *knowledge* a speaker has (competence), psycholinguistics asks how that
knowledge is *used* (performance): what happens, moment by moment and in the brain,
when we understand a sentence or plan an utterance.

## Comprehension and production

Language use has two directions:

- **Comprehension** runs from signal to meaning: recognizing sounds
  (see [phonetics-and-phonology](phonetics-and-phonology.md)), retrieving words,
  building syntactic structure (see [syntax](syntax.md)), and computing meaning
  (see [semantics](semantics.md)) and speaker intent
  (see [pragmatics](pragmatics.md)).
- **Production** runs the other way: from an intended message to conceptual
  planning, word selection, grammatical encoding, and articulation.

Both happen fast — comprehension is largely **incremental**, meaning listeners build
interpretations word by word rather than waiting for a sentence to end.

## The mental lexicon

The **mental lexicon** is the brain's dictionary: the store of words with their sounds,
meanings, and grammatical properties. It is not an alphabetized list but an associative
network, accessed astonishingly quickly. A key tool for probing it is **priming**:
encountering *doctor* speeds recognition of the related *nurse*, revealing that lexical
access spreads activation through semantically and phonologically linked entries. This
associative, distributional organization is the psychological counterpart of the
distributional word representations used in NLP
(see [../ai/representation-learning-and-embeddings.md](../ai/representation-learning-and-embeddings.md)).

## Parsing and garden-path sentences

**Parsing** is the process of assigning syntactic structure during comprehension.
Because parsing is incremental and the parser commits early, it can be led astray.
**Garden-path sentences** are the classic demonstration:

> *The horse raced past the barn fell.*

Readers initially parse *raced* as the main verb, hit *fell*, and must reanalyze
(*raced past the barn* is a reduced relative clause). The momentary breakdown exposes
the parser's strategies — its preference for simpler structures and its reliance on
probabilistic expectations built from experience. This makes human parsing a study in
**prediction**: readers continuously anticipate upcoming material, and processing
difficulty tracks how surprising a word is given its context.

## Why it matters — the tie to sequence models and LLMs

That last point is where psycholinguistics and modern AI meet most directly.
**Surprisal theory** holds that reading time is proportional to a word's information
content — how improbable it is given the preceding context. Because sequence models
(see [../ai/sequence-models-and-rnns.md](../ai/sequence-models-and-rnns.md)) and large
language models (see [../ai/large-language-models.md](../ai/large-language-models.md))
are trained precisely to estimate the probability of the next word, their surprisal
estimates predict human reading times and neural responses remarkably well, and LLMs
have become a standard instrument for generating these predictions. The
incremental, predictive character of human comprehension turns out to rhyme with
next-token prediction. Psycholinguistics also connects to how language is realized in
the brain (see [../neuroscience/index.md](../neuroscience/index.md)) and to how
processing capacity develops in
[language-acquisition](language-acquisition.md); its methods are among the ways we test
claims from [universal-grammar](universal-grammar.md) against real-time behavior.

## References

- Concept note — synthesized from the psycholinguistics literature; no single source.
  Related canonical works:
  [fromkin-introduction-to-language](fromkin-introduction-to-language.md),
  [pinker-language-instinct](pinker-language-instinct.md).
