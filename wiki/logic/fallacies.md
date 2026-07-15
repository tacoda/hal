---
type: Concept
title: Fallacies
tags: [logic, fallacies, formal-fallacies, informal-fallacies, reasoning-errors, critical-thinking, rhetoric]
timestamp: 2026-07-14
---

# Fallacies

A **fallacy** is a defect in an argument that makes it fail to support its conclusion, while
often *appearing* to. The "appearing to" is the whole point: a merely false statement is not
a fallacy, and a transparently bad argument fools no one. Fallacies matter precisely because
they are persuasive — they exploit the shortcuts, emotions, and surface patterns that make
faulty reasoning *feel* sound. Learning them is learning the standard failure modes of the
[arguments](informal-logic-and-argumentation.md) people actually make, so you can name a bad
move instead of just sensing that something is off.

Fallacies split into two families by *where* the defect lives.

## Formal fallacies

A **formal fallacy** is a broken *structure*: the argument's form is invalid, so the
premises fail to guarantee the conclusion regardless of their content. These are detectable
by inspecting the shape alone, which is why they are the province of
[propositional logic](propositional-logic.md). The two classics both misuse a conditional
"if P then Q":

| Fallacy | Bad form | Why it fails |
|---|---|---|
| **Affirming the consequent** | If P then Q; Q; therefore P | Q can have other causes; the rain wets the street, but a street may be wet without rain |
| **Denying the antecedent** | If P then Q; not-P; therefore not-Q | P being false does not close off other routes to Q |

Both are near-mirrors of the *valid* forms — *modus ponens* (P → Q, P, ∴ Q) and *modus
tollens* (P → Q, ¬Q, ∴ ¬P) — which is exactly why they slip past: they borrow the shape of a
correct inference. A truth table settles the matter mechanically: there is a row where the
premises are true and the conclusion false, so the form is invalid.

## Informal fallacies

An **informal fallacy** has an acceptable-looking structure but a defect in *content,
relevance, or presumption*. You cannot catch these by inspecting form; you have to read what
is being said. They divide roughly into fallacies of **relevance** (the premises are beside
the point), of **weak induction** (the evidence is too thin), and of **presumption,
ambiguity, or question-begging** (a premise smuggles in what it should establish).

**Fallacies of relevance** — the premises push emotional or social buttons instead of
bearing on the claim:

- **Ad hominem** — attacking the arguer rather than the argument ("you would say that,
  you're a lobbyist"). A person's flaws leave their argument's merits untouched.
- **Straw man** — refuting a distorted, weaker version of the opponent's position instead of
  the real one. The disciplined antidote is the [principle of
  charity](informal-logic-and-argumentation.md).
- **Appeal to authority** — citing an authority who is unqualified, biased, or outside their
  domain. (Citing a *genuine, relevant* expert is legitimate — the fallacy is the misuse.)
- **Appeal to emotion** — substituting fear, pity, flattery, or outrage for evidence.

**Fallacies of weak induction** — the inference outruns the evidence:

- **Slippery slope** — claiming one step must trigger a chain to some extreme outcome,
  without establishing that each link actually follows.
- **Correlation implies causation** — treating co-occurrence as proof of a causal link. Two
  things moving together may share a common cause or be pure coincidence; establishing
  causation takes more, as [causal inference](../statistics/causal-inference.md) spells out
  in full. This one deserves special vigilance because data-rich, machine-assisted analysis
  produces correlations by the thousand, and the temptation to narrate them causally is
  enormous.
- **False dilemma** (false dichotomy) — presenting two options as exhaustive when others
  exist ("either we cut the program or we go bankrupt"). It weaponizes a genuinely valid
  form (disjunctive syllogism) by supplying a false disjunction.

**Fallacies of presumption and ambiguity** — a premise is defective or does its work by a
trick of language:

- **Begging the question** (petitio principii) — assuming the conclusion among the premises,
  so the argument moves in a circle ("the drug is safe because it has no harmful effects").
- **Equivocation** — trading on two meanings of a single word within one argument ("a
  feather is light; what is light cannot be dark; so a feather cannot be dark").

## Why fallacies persuade

Fallacies survive because they are *usually* attached to reasoning that is otherwise fluent
and confident, and because most of them are corruptions of legitimate moves: appeal to
authority parasitizes real expert testimony, false dilemma parasitizes valid disjunction,
affirming the consequent parasitizes *modus ponens*. They also exploit cognitive shortcuts —
we defer to authority, fear extremes, and read fluency as truth. That last shortcut is why
fallacy-spotting is now a survival skill for reading
[large language model](../ai/large-language-models.md) output: a model generates prose that
is maximally fluent and confident by construction, so surface polish carries even less
information about soundness than usual. The remedy is not intuition but the deliberate
discipline of [critical thinking in the age of
AI](../ai-org/critical-thinking-during-the-age-of-ai.md).

## Spotting them

A working procedure:

1. **Find the conclusion and the premises**, making implicit ones explicit.
2. **Check the form** first — is it a valid deductive shape, or one of the formal fallacies?
3. **If the form is fine, test relevance and evidence** — do the premises actually bear on
   the claim, and is the inductive support strong enough for the strength of the conclusion?
4. **Check for smuggled assumptions** — does a premise already assume the conclusion, or
   shift the meaning of a key term?
5. **Name the move.** Naming forces precision and turns a vague unease into a specific,
   answerable objection — which is what lets the argument be repaired rather than merely
   dismissed.

The goal is not to collect a bingo card of Latin names to fling at opponents (calling
everything a fallacy is itself a rhetorical dodge), but to reason and read more carefully,
and to demand better arguments — including from yourself.

## References

- [Hurley, *A Concise Introduction to Logic*](hurley-concise-introduction-to-logic.md) —
  the anchoring text; its fallacy taxonomy underlies the organization here.
