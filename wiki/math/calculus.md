---
type: Concept
title: Calculus
tags: [math, calculus, limits, derivatives, integrals, taylor-series, analysis]
timestamp: 2026-07-14
---

# Calculus

Calculus is the mathematics of **continuous change**. Where
[linear-algebra.md](linear-algebra.md) handles the discrete and the linear, calculus handles
smooth variation: how a quantity changes instant to instant (the **derivative**) and how those
changes accumulate (the **integral**). This note covers the single-variable case;
[multivariable-calculus.md](multivariable-calculus.md) extends it to many dimensions, which is
where it powers modern AI.

## Limits and continuity

Everything in calculus rests on the **limit**: the value a function $f(x)$ approaches as $x$
approaches some point $a$, written $\lim_{x\to a} f(x)$. The limit lets us talk rigorously
about "getting arbitrarily close" without ever requiring $x$ to equal $a$. A function is
**continuous** at $a$ when $\lim_{x\to a} f(x) = f(a)$ — no jumps, gaps, or blowups. The
$\varepsilon$–$\delta$ definition that makes this airtight is the entry point to
[real-analysis.md](real-analysis.md), and getting it right requires the proof discipline of
[mathematical-proof-and-logic.md](mathematical-proof-and-logic.md).

## The derivative

The **derivative** measures instantaneous rate of change — the slope of the tangent line. It
is defined as a limit of slopes of secant lines:

$$ f'(x) = \lim_{h\to 0} \frac{f(x+h) - f(x)}{h}. $$

The rules of differentiation (power, product, quotient, and especially the **chain rule** for
compositions, $\,(f\circ g)' = (f'\circ g)\cdot g'$) make it mechanical to differentiate almost
any expression. The chain rule is not a footnote: it is the single fact that
[../ai/backpropagation-and-gradient-descent.md](../ai/backpropagation-and-gradient-descent.md)
is built on, applied recursively through the layers of a
[../ai/neural-networks.md](../ai/neural-networks.md).

## The integral and the Fundamental Theorem

The **integral** $\int_a^b f(x)\,dx$ accumulates a quantity — geometrically, the signed area
under the curve — defined as a limit of Riemann sums that partition the interval into ever-finer
slices. Differentiation and integration look like unrelated operations (rates vs. totals), and
the great result of the subject, the **Fundamental Theorem of Calculus**, says they are exact
inverses:

$$ \int_a^b f'(x)\,dx = f(b) - f(a), \qquad \frac{d}{dx}\int_a^x f(t)\,dt = f(x). $$

This is what makes integrals computable: instead of summing infinitely many slices, you find an
antiderivative and evaluate it at the endpoints.

## Taylor series

A smooth function can be approximated near a point $a$ by a polynomial built from its
derivatives there — its **Taylor series**:

$$ f(x) \approx f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \dots $$

Truncating after the first-order term is the **linear approximation** — the idea that a smooth
function looks locally like a line — and this is *precisely* the assumption that justifies taking
a small gradient step in optimization. Second-order (curvature) information from $f''$ underlies
Newton's method and the Hessian-based reasoning in
[multivariable-calculus.md](multivariable-calculus.md).

## Example

Let $f(x) = x^2$. Then $f'(x) = 2x$, so the slope at $x=3$ is $6$: near $x=3$ the curve rises
about $6$ units for every unit of $x$. Integrating back, $\int_0^3 2x\,dx = [x^2]_0^3 = 9 = f(3)-f(0)$
— the Fundamental Theorem closing the loop between the rate ($2x$) and the accumulated total.

## Why it matters (and the AI role)

Calculus turns "optimize this model" into a solvable problem. Training any
[../ai/machine-learning.md](../ai/machine-learning.md) model means minimizing a loss function,
and the derivative tells you which way is downhill. In the single variable this is finding where
$f'(x) = 0$; in the millions of parameters of
[../ai/deep-learning.md](../ai/deep-learning.md) it becomes the gradient descent of
[../ai/backpropagation-and-gradient-descent.md](../ai/backpropagation-and-gradient-descent.md),
which is just this chapter's derivative and chain rule scaled up by
[multivariable-calculus.md](multivariable-calculus.md). Calculus also underwrites probability
densities used in [../statistics/index.md](../statistics/index.md) and the dynamics of
[differential-equations.md](differential-equations.md).

## References

- [Calculus](spivak-calculus.md) — Michael Spivak (rigorous single-variable calculus)
- [Principles of Mathematical Analysis](rudin-principles-of-mathematical-analysis.md) — Walter Rudin (the analytic foundations)
