---
type: Concept
title: Morphology
tags: [linguistics, morphology, morphemes, inflection, derivation, tokenization]
timestamp: 2026-07-14
---

# Morphology

**Morphology** is the study of word structure: how words are built from smaller
meaning-bearing pieces. It sits between
[phonetics-and-phonology](phonetics-and-phonology.md) (which supplies the sounds) and
[syntax](syntax.md) (which arranges the finished words), and it explains why *unhappiness*,
*cats*, and *rewrite* feel like assembled things rather than atoms.

## The morpheme

The basic unit is the **morpheme**: the smallest linguistic unit that carries meaning or
grammatical function. *Cats* is two morphemes — *cat* (the meaning) plus *-s* (plural).
Morphemes come in two kinds:

- **Free morphemes** can stand alone as words (*cat*, *run*, *blue*).
- **Bound morphemes** cannot; they must attach to something (*-s*, *un-*, *-ness*, *-ing*).

Bound morphemes are **affixes**, attaching to a **root** or **stem**: *prefixes* precede
(*un-do*), *suffixes* follow (*kind-ness*), and some languages use *infixes* (inside the
root) or *circumfixes* (wrapping it). A **root** is the core lexical morpheme; a **stem** is
whatever a further affix attaches to (in *un-friend-li-ness*, *friend* is the root, and
each layer forms a new stem).

## Inflection vs derivation

The most important split in morphology:

- **Inflectional morphology** adjusts a word for its grammatical context without changing
  its part of speech or core meaning: plural *-s*, past tense *-ed*, comparative *-er*.
  English has only a handful of inflections; languages like Finnish, Turkish, or Latin have
  rich inflectional systems (a Finnish noun has ~15 cases). Inflection is
  grammar-driven and largely obligatory — you *must* mark the plural.
- **Derivational morphology** creates a new word, often changing the part of speech or
  meaning: *happy* → *happiness* (adjective → noun), *legal* → *illegal* (reverses
  meaning), *nation* → *national* → *nationalize* → *nationalization*. Derivation is
  optional and lexical — it builds the vocabulary.

**Productivity** measures how freely a morpheme combines with new bases. *-ness* and *-able*
are highly productive (you can coin *googleable* and be understood); *-th* (as in *warmth*,
*width*) is frozen. Productivity is why native speakers instantly parse and pronounce words
they have never seen — the generative capacity [pinker](pinker-language-instinct.md)
highlights as evidence that word-building is rule-governed, not memorized item-by-item.

Languages differ in *morphological typology*: **isolating** languages (Mandarin) use few
morphemes per word; **agglutinative** languages (Turkish) stack many clear-cut affixes;
**fusional** languages (Latin) pack several grammatical meanings into one hard-to-segment
affix. See [fromkin-introduction-to-language.md](fromkin-introduction-to-language.md)
for the full typology.

## Why it matters — and the NLP echo

Morphology is where the **tokenization** problem in NLP comes from. A model must decide
what counts as a unit of text. Splitting on whitespace treats *run*, *runs*, *running*, and
*ran* as four unrelated symbols, exploding the vocabulary and hiding the shared root — a
disaster for a morphologically rich language where one lemma yields dozens of forms.

Modern [../ai/large-language-models.md](../ai/large-language-models.md) sidestep this with
**subword tokenization** (Byte-Pair Encoding, WordPiece, Unigram / SentencePiece). These
algorithms learn, from raw text frequency, to break words into recurring chunks —
*tokenization* might become *token* + *ization*, *unhappiness* into *un* + *happi* + *ness*.
This is a *statistical* rediscovery of exactly the affix/root decomposition morphology
describes: the model gets a compact vocabulary, handles unseen words gracefully, and shares
representation across related forms. The chunks are then mapped to
[../ai/representation-learning-and-embeddings.md](../ai/representation-learning-and-embeddings.md)
so morphologically related words land near each other in vector space. Subwords are not
true morphemes — BPE will happily split on a boundary no linguist would draw — but the
success of the approach is a real vindication of the morphological insight that words have
internal, reusable structure.

Morphology also feeds [semantics](semantics.md) (derivation composes meaning) and
[psycholinguistics](psycholinguistics.md) (how the brain stores and retrieves complex
words), and morphological change is a driver in
[historical-linguistics](historical-linguistics.md).

## References

- [fromkin-introduction-to-language.md](fromkin-introduction-to-language.md)
- [pinker-language-instinct.md](pinker-language-instinct.md)
- [jurafsky-martin-speech-and-language-processing.md](jurafsky-martin-speech-and-language-processing.md)
