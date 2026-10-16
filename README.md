# Classical invariant theory

**Provisional repository name: Synectic.** The owner intends to rename it. The subject is **classical invariant theory**, especially nineteenth-century mathematics: how mathematicians constructed polynomial expressions that remain unchanged, or transform by a prescribed factor, when their variables are changed.

Start with the actual nineteenth-century objects and their original names, not solely with today's textbook account of matrices or linear operators.

## What is invariant, and under which transformations?

Take a binary quadratic form

```text
f(x, y) = ax² + 2bxy + cy².
```

An invertible linear substitution of the variables changes `a,b,c`. The quantity `b² − ac` generally changes too, but predictably: it is multiplied by `det(g)²` under `(x,y) ↦ g(x,y)`. Thus it is a **relative invariant under GL₂** and an **invariant under SL₂**.

This distinction is essential: specify the object, the group acting on it, and the transformation law before calling something “invariant.”

For comparison, the characteristic polynomial of an endomorphism is invariant under **similarity**. It is not generally preserved by independent changes of input and output bases.

## Nineteenth-century objects and methods to reconstruct

- **Binary forms**, transformations of variables, invariants and *relative* invariants, covariants, and concomitants
- **Determinants, discriminants, resultants, Bézoutians, and catalecticants**
- **Hessians, Jacobians, polar operations, and transvectants**
- **Symbolic/bracket methods, apolarity, and decomposition of forms into powers**
- **Syzygies** among invariants and covariants, and finite generation
- Historical links to **Boole, Cayley, Sylvester, Hermite, Aronhold, Clebsch, Gordan, Hilbert**, and others
- Why those particular coefficient arrays and determinant formulas arise, and which constructions remain meaningful without a chosen basis

A good test case is the catalecticant of a binary quartic written with binomial coefficients:

```text
f(x,y) = ax⁴ + 4bx³y + 6cx²y² + 4dxy³ + ey⁴.

                  ┌           ┐
Cat(f) = determinant │ a  b  c │
                  │ b  c  d │
                  │ c  d  e │
                  └           ┘
```

Study why this particular Hankel-type array arises, what the vanishing of its determinant means (including the distinction between a sum-of-powers decomposition and a limit of such decompositions), and its exact transformation law.

## Reading and active notes

- [From determinants to matrices: why are there entries?](notes/determinants-to-matrices.md) — determinant-first history, change of bases, and what is or isn't intrinsic
- [R. Skip Garibaldi, *The Characteristic Polynomial and Determinant Are Not Ad Hoc Constructions*](sources/skip-garibaldi-characteristic-polynomial.md) — related reading about intrinsic algebraic constructions, not a claim that characteristic polynomials exhaust classical invariant theory
- [Borcherds's algebraic geometry lectures, notes taken by Zvi Rosen, §14.2, p. 40](https://www2.math.upenn.edu/~zvihr/courses/AGNotes.pdf) — mentions Sylvester's “determinant, resultant, Bezoutiant, catalecticant, harmonizant” and discusses elimination
- [Karen H. Parshall, historical account of Sylvester's catalecticant, especially the binary quartic](https://www.numdam.org/item/10.24033/rhm.90.pdf)
- [Kung and Rota, *The Invariant Theory of Binary Forms*](https://doi.org/10.1090/S0273-0979-1984-15188-7) — symbolic methods, apolarity, finite generation
- [Peter J. Olver, *Classical Invariant Theory*](https://www.cambridge.org/core/books/classical-invariant-theory/8E27C3320CA61660F0866752299B2D0E) — modern reference, including transvectants and graphical methods

An older [verse-and-mathematics reading note](sources/verse-and-mathematics.md) is retained as tangential historical material. Poetry is **not** the organizing subject of this repository.

## Method

1. Find the original paper and identify the author's actual definition, worked examples, and purpose.
2. Specify the group action and whether an expression is invariant, relatively invariant, or covariant.
3. Derive the nineteenth-century formula, *then* compare it with coordinate-free and modern algebraic interpretations.
4. Keep historical attributions separate from modern reconstructions; avoid calling two objects “the same” without specifying an equivalence relation.
