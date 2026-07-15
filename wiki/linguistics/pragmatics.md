---
type: Concept
title: Pragmatics
tags: [linguistics, pragmatics, speech-acts, grice, implicature, deixis, alignment]
timestamp: 2026-07-14
---

# Pragmatics

**Pragmatics** is the study of meaning in *context* — what speakers mean as opposed to what
their words literally say. Where [semantics](semantics.md) gives the context-free,
truth-conditional meaning of a sentence, pragmatics explains how listeners get from that
literal content to the speaker's actual intent using the situation, shared knowledge, and
principles of cooperative communication. When you answer *"Can you pass the salt?"* by
passing the salt rather than saying *"Yes, I can,"* you have done pragmatics.

## Speech acts

**Speech act theory** (Austin, Searle) observes that saying something is often *doing*
something. Austin distinguished three layers of an utterance:

- **Locutionary act** — the literal words and their semantic meaning.
- **Illocutionary act** — the intended function: asserting, requesting, promising,
  warning, apologizing. This is the act the speaker performs *in* speaking.
- **Perlocutionary act** — the effect on the hearer (persuading, alarming, reassuring).

The illocutionary force can diverge sharply from the surface form: *"It's cold in here"* is
grammatically a statement but may function as a request to close the window — an **indirect
speech act**. Recovering illocutionary force is central to understanding dialogue.

## Grice's maxims and implicature

Paul Grice's **Cooperative Principle** is the engine of pragmatic inference: participants in
conversation assume each other is being cooperative — making contributions as informative,
truthful, relevant, and clear as required. He spelled this out as four **maxims**:

- **Quantity** — be as informative as needed, no more.
- **Quality** — say what you believe true and can support.
- **Relation** — be relevant.
- **Manner** — be clear, brief, orderly; avoid ambiguity.

The theoretical payoff is **conversational implicature**: meaning conveyed *beyond* the
literal, inferred from the assumption of cooperation. Asked *"Did you like the film?"* and
answered *"Well, the popcorn was fresh,"* you infer the speaker did **not** like the film —
because a cooperative, relevant reply that pointedly avoids the question implies a negative.
Nothing in the semantics says this; the implicature comes from reasoning about *why* the
speaker chose those words. Implicatures are **cancellable** (*"…and the film was great too"*
retracts it), which distinguishes them from literal entailments.

## Deixis and presupposition

- **Deixis** — expressions whose reference depends entirely on the utterance context:
  *I*, *you*, *here*, *there*, *now*, *tomorrow*, *this*. *"Meet me here tomorrow"* is
  uninterpretable without knowing who is speaking, where, and when. Deixis is the clearest
  case of meaning that semantics alone cannot fix — it *requires* context.
- **Presupposition** — background assumed true for an utterance to make sense. *"Have you
  stopped procrastinating?"* presupposes you were procrastinating; the presupposition
  survives even when the sentence is negated or questioned, which is what distinguishes it
  from ordinary asserted content.

## Why it matters — dialogue and LLM alignment

Pragmatics is where language meets social cognition, so it is the linguistic layer most
directly implicated in conversational AI. A system that handles only
[semantics](semantics.md) answers *"Can you pass the salt?"* with *"Yes"* — literally
correct, pragmatically useless. Useful dialogue demands modeling illocutionary force,
tracking presuppositions, and drawing Gricean implicatures.

This maps tightly onto the behavior we want from
[../ai/large-language-models.md](../ai/large-language-models.md). A base model trained only
on next-token prediction ([../ai/transformers-and-attention.md](../ai/transformers-and-attention.md))
absorbs enormous pragmatic *regularity* from text but has no built-in commitment to being
cooperative, truthful, or relevant. **Alignment** techniques — instruction tuning and
reinforcement learning from human feedback (RLHF) — can be read as *teaching a model
Grice's maxims*: be as informative as needed (Quantity), do not fabricate (Quality), stay
on topic (Relation), be clear (Manner). Failures of aligned models are largely pragmatic
failures — hallucination is a Quality violation, waffling is a Quantity/Manner violation,
missing an indirect request is an illocutionary-force failure. The framework Grice built to
explain human conversation turns out to be a remarkably precise specification of what a
"helpful assistant" is supposed to do, which is why pragmatics is arguably the most
practically important level of linguistics for current AI.

Pragmatics also connects to [sociolinguistics](sociolinguistics.md) (politeness,
register, and context vary by social setting) and to the
[../philosophy/index.md](../philosophy/index.md) of language (intention, meaning, and
convention). The standard textbook treatment is in
[fromkin-introduction-to-language.md](fromkin-introduction-to-language.md), and dialogue
systems and pragmatic phenomena are covered computationally in
[jurafsky-martin-speech-and-language-processing.md](jurafsky-martin-speech-and-language-processing.md).

## References

- [fromkin-introduction-to-language.md](fromkin-introduction-to-language.md)
- [jurafsky-martin-speech-and-language-processing.md](jurafsky-martin-speech-and-language-processing.md)
