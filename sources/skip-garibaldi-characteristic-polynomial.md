# R. Skip Garibaldi — *The Characteristic Polynomial and Determinant Are Not Ad Hoc Constructions*

**Citation:** R. Skip Garibaldi, *The Characteristic Polynomial and Determinant Are Not Ad Hoc Constructions*, **American Mathematical Monthly** 111 (2004), no. 9, 761–778.

- [Open preprint: arXiv:math/0203276](https://arxiv.org/abs/math/0203276)
- [Journal article (DOI)](https://doi.org/10.1080/00029890.2004.11920140)

## Why read it?

It addresses the central Synectic question: **why does the characteristic polynomial have the form it does, and what is intrinsic before we arrange coefficients into a matrix?**

The familiar formula `χ_A(x) = det(xI − A)` is useful, but it puts the determinant first. Garibaldi reverses the construction: define the characteristic polynomial using the **minimal polynomial of a generic element of an algebra**, then obtain an appropriate determinant from its constant term.

The underlying idea goes back to the late nineteenth century, as Garibaldi explicitly acknowledges (see his introduction and references to Study 1889 and an 1891 source). This is not a claim that the paper's construction originated in 2004.

## The construction

Let `𝓐` be a finite-dimensional, associative, unital algebra over a field `F`. Choose an `F`-basis `a₁, …, aₘ` and introduce independent indeterminates `t₁, …, tₘ`.

```text
R ← F[t₁, …, tₘ]
K ← F(t₁, …, tₘ)

γ ← t₁a₁ + ⋯ + tₘaₘ   ∈ 𝓐 ⊗_F K
```

The element `γ` is **generic**: its coordinates are indeterminates rather than specially chosen numbers. Compute its monic minimal polynomial `m_γ(x)` over `K`. Its coefficients actually lie in `R`; specializing `tᵢ → αᵢ` for a particular element `a = Σ αᵢaᵢ` yields the **characteristic polynomial of a in 𝓐**.

Garibaldi proves that the result is independent of the basis used to construct `γ` (Proposition 1.6). It depends on the element **and the ambient algebra**.

For `𝓐 = Mₙ(F)`, this construction gives exactly `det(xI − A)`, but the determinant is not part of its definition. An analogous construction extends beyond matrix algebras; the paper also discusses power-associative algebras.

## Our running example

```text
A = ┌       ┐
    │ 2  −1 │
    │ 1   3 │
    └       ┘

χ_A(x) = x² − 5x + 7
```

Its coefficients are independent of the **single basis** chosen to express the operator `T:V → V`; an operator basis change gives `A′ = P⁻¹AP`. They are *not* invariant under arbitrary independent changes of domain and codomain bases.

Notice the distinction between **minimal polynomial of a specific matrix** and **specialization of the minimal polynomial of a generic matrix**. For example, the minimal polynomial of the 2×2 identity is `x − 1`, while its characteristic polynomial is `(x − 1)²`.

The ambient algebra matters too: the element `1` in `F` has characteristic polynomial `x − 1`, whereas the corresponding scalar identity matrix in `M₂(F)` has `(x − 1)²`.

## Questions to pursue

1. Work through Garibaldi's proof that the generic minimal polynomial has polynomial coefficients and is independent of the basis.
2. Reconstruct the 2×2 generic-matrix argument *without defining determinant first*.
3. Identify precisely the differences between similarity invariants (characteristic polynomial), equivalence invariants (rank for fixed dimensions), and relative invariants of binary forms (catalecticant).
4. Follow the nineteenth-century predecessors Garibaldi cites, including their original terminology.
5. Compare his approach to the exterior-power construction of determinant and to the determinant-first practices of Sylvester and Cayley.

This is a reading note and conceptual map, not a replacement for the full argument in the linked paper.
