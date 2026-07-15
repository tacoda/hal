---
type: Reference
title: Speech and Language Processing (Jurafsky & Martin)
tags: [nlp, computational-linguistics, textbook, language-models, transformers, speech]
timestamp: 2026-07-14
source: https://web.stanford.edu/~jurafsky/slp3/
---

# Speech and Language Processing

Dan Jurafsky and James H. Martin's *Speech and Language Processing* is the canonical
textbook of the field — the "NLP bible" — used in graduate and advanced-undergraduate
courses worldwide. The third edition is written as an evolving free draft: individual
chapters and a single combined PDF are posted and revised continuously (the January 2026
draft, for instance, restructured the language-model material, added chapters on automatic
speech recognition and text-to-speech, and updated the transformer figures). It sits at the
intersection of [computational linguistics and NLP](computational-linguistics-and-nlp.md)
and machine learning, treating language technology as an engineering discipline grounded in
linguistic structure.

## Scope

The book spans the full pipeline from raw text and speech to meaning and generation, and
its third-edition arc mirrors the field's own shift from symbolic/statistical methods to
neural models:

- **Foundations** — regular expressions, text normalization, edit distance, and
  Unicode; the mechanics of turning strings into tractable units.
- **Language modeling** — from **n-gram** models (the classical count-based, Markov view
  of predicting the next word) to modern neural and large-language-model approaches. This
  progression is the book's through-line: the same task (assign probability to a sequence)
  solved with successively more powerful machinery.
- **Representations and sequence models** — word embeddings, recurrent networks, and the
  **[transformer](../ai/transformers-and-attention.md)** architecture that now dominates,
  leading into **[large language models](../ai/large-language-models.md)**, pretraining,
  fine-tuning, and alignment techniques such as DPO.
- **Linguistic structure** — part-of-speech tagging, [morphology](morphology.md),
  parsing and [syntax](syntax.md), lexical and compositional
  [semantics](semantics.md), coreference, and discourse.
- **Applications** — information extraction, machine translation, question answering,
  dialogue, chatbots, and the **speech** stack: phonetics, ASR, and TTS.

## Why it matters

Where *Syntactic Structures* asks what the human grammar *is*, Jurafsky & Martin ask how a
*machine* can process language — and answers by weaving linguistic theory together with
probability, information theory, and deep learning. Its enduring value is that it teaches
the linguistic problem *and* the current computational solution side by side, so a reader
understands why, say, part-of-speech ambiguity or long-distance dependency is hard before
seeing the model that handles it. Because the third edition is revised in near-real time,
it is one of the few textbooks that tracks the LLM era as it unfolds, connecting decades of
NLP foundations to the transformer-based systems now in production.

## References

- [Speech and Language Processing (3rd ed. draft) — Jurafsky & Martin](https://web.stanford.edu/~jurafsky/slp3/)
