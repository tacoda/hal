---
type: Concept
title: Linear Algebra
tags: [math, linear-algebra, vectors, matrices, eigenvalues, svd, machine-learning]
timestamp: 2026-07-14
---

# Linear Algebra

Linear algebra is the study of **vectors**, **vector spaces**, and the **linear maps**
between them. It is the working language of machine learning and data science: a dataset is
a matrix, a model layer is a matrix multiply, and an embedding is a point in a vector space.
If you understand linear algebra, most of the notation in
[../ai/deep-learning.md](../ai/deep-learning.md) stops being intimidating and starts being
mechanical.

## Vectors and vector spaces

A **vector** is an element of a vector space — an ordered list of numbers
$\mathbf{x} = (x_1, \dots, x_n) \in \mathbb{R}^n$ that you can add together and scale by
real numbers. A **vector space** is any set closed under those two operations (with the
usual rules). Geometrically an $n$-vector is a point or arrow in $n$-dimensional space; in
data terms it is one example described by $n$ features.

Key structural ideas:

- **Span** — the set of all linear combinations $c_1\mathbf{v}_1 + \dots + c_k\mathbf{v}_k$
  of a collection of vectors. It is the subspace they "reach".
- **Linear independence** — no vector in the set is a combination of the others; none is
  redundant.
- **Basis** — a linearly independent set that spans the whole space. Every vector has a
  *unique* coordinate representation in a given basis.
- **Dimension** — the number of vectors in any basis. An invariant of the space.

These concepts are made precise abstractly in
[axler-linear-algebra-done-right.md](axler-linear-algebra-done-right.md), which builds the
theory from linear maps rather than from matrices — and they rest on the
[set-theory.md](set-theory.md) notion of a set and the reasoning discipline of
[mathematical-proof-and-logic.md](mathematical-proof-and-logic.md).

## Matrices and linear maps

A **linear map** $T$ satisfies $T(a\mathbf{x} + b\mathbf{y}) = aT(\mathbf{x}) + bT(\mathbf{y})$ —
it preserves addition and scaling. The central theorem of the subject is that, once you fix
bases, every linear map between finite-dimensional spaces *is* a **matrix**, and composing
maps *is* multiplying matrices.

**Matrix multiplication** $C = AB$ is defined so that applying $A$ then $B$ to a vector
equals applying the single matrix $BA$. Concretely, $(AB)_{ij} = \sum_k A_{ik} B_{kj}$ — a
row of $A$ dotted with a column of $B$. It is associative but *not* commutative, and its
$O(n^3)$ cost (for naive $n \times n$ multiply) is why GPUs and specialized kernels exist:
the forward pass of a [../ai/neural-networks.md](../ai/neural-networks.md) is essentially a
stack of matrix multiplies interleaved with nonlinearities.

- **Rank** — the dimension of a matrix's column space (equivalently row space): how many
  independent directions the map actually produces. Low rank means information is being
  compressed.
- **Systems of equations** $A\mathbf{x} = \mathbf{b}$ — solved by Gaussian elimination.
  Whether a solution exists and is unique is entirely a question about rank and span.
- **Determinant** — a single scalar $\det(A)$ measuring the signed volume-scaling factor of
  the map; $\det(A) = 0$ exactly when $A$ is singular (non-invertible, collapses volume).

[strang-linear-algebra.md](strang-linear-algebra.md) is the canonical concrete,
application-first treatment of all of the above.

## Eigenvalues, eigenvectors, and SVD

An **eigenvector** $\mathbf{v}$ of a square matrix $A$ is a direction the map only *stretches*,
never rotates: $A\mathbf{v} = \lambda \mathbf{v}$, where the scalar $\lambda$ is its
**eigenvalue**. Eigenvectors reveal a map's intrinsic axes. Diagonalizing $A = Q \Lambda Q^{-1}$
in its eigenbasis turns hard operations (like matrix powers, central to
[differential-equations.md](differential-equations.md) and Markov chains) into trivial ones
on the diagonal $\Lambda$.

The **Singular Value Decomposition (SVD)** generalizes this to *any* matrix:

$$ A = U \Sigma V^\top $$

where $U, V$ are orthogonal and $\Sigma$ is diagonal with non-negative **singular values**.
SVD is arguably the most useful factorization in applied math: it powers **principal
component analysis** (see [../statistics/index.md](../statistics/index.md)), low-rank
approximation, dimensionality reduction, and recommender systems. Truncating to the largest
singular values gives the best low-rank approximation of a matrix — the mathematical heart of
compression and denoising.

## Example

Consider rotating the plane by 90°. As a linear map it sends $(1,0)\mapsto(0,1)$ and
$(0,1)\mapsto(-1,0)$, so its matrix is
$R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$. Its determinant is $1$ (rotation
preserves area), and it has *no real* eigenvectors (every direction genuinely rotates), which
shows up as complex eigenvalues $\pm i$ — a clean illustration of how the algebra encodes the
geometry, connecting to [number-theory.md](number-theory.md) and the complex numbers.

## Why it matters (and the AI role)

Linear algebra is the substrate of modern AI. Every layer of a
[../ai/neural-networks.md](../ai/neural-networks.md) is an **affine map** $\mathbf{z} = W\mathbf{x} + \mathbf{b}$
followed by a nonlinearity; training via
[../ai/backpropagation-and-gradient-descent.md](../ai/backpropagation-and-gradient-descent.md)
propagates gradients through those maps using the Jacobian (a matrix), a computation grounded
in [multivariable-calculus.md](multivariable-calculus.md). Embeddings place words, images, and
users as vectors so that *semantic similarity becomes geometric proximity*
(a dot product). Attention in transformers is a sequence of matrix products. Whether the field
is [../ai/machine-learning.md](../ai/machine-learning.md), computer graphics, or scientific
computing, linear algebra is the layer everything else is built on — and the bridge into the
convex, matrix-shaped world of [../linear-optimization/index.md](../linear-optimization/index.md).

## References

- [Introduction to Linear Algebra](strang-linear-algebra.md) — Gilbert Strang (concrete, applied)
- [Linear Algebra Done Right](axler-linear-algebra-done-right.md) — Sheldon Axler (map-centric theory)
