# From determinants to matrices: why do matrices have entries?

## The question

An array of numbers is a very convenient way of describing a linear transformation. But why **this** form? Why rows and columns? What are its entries *about*? Which properties belong to the underlying mathematical object, and which to our method of recording it?

The historical development suggests that matrices were not inevitable starting objects. Determinants were studied before a general matrix algebra was formulated, and rectangular collections of coefficients initially served several purposes. Do not impose a single modern story on these different investigations.

## Historical starting points

**Cramer (1750):** Coefficients and determinants appear in methods for solving simultaneous equations. Do not claim that Cramer thought in terms of exterior powers or oriented volume unless direct textual evidence establishes it. Nor was he the first person in history to use rectangular numerical arrangements.

**Sylvester (1850):** In *“Additions to the Articles ‘On a New Class of Theorems,’ and ‘On Pascal's Theorem’”*, *Philosophical Magazine*, 37, 363–370 (especially p. 369), a **matrix** is an oblong arrangement from which determinants may be obtained by selecting rows and columns. Here the array is a generator of minors. Compare his paper directly against the reprint in *The Collected Mathematical Papers*, vol. 1, p. 150.

**Cayley (1858):** In *“A Memoir on the Theory of Matrices”*, *Philosophical Transactions of the Royal Society of London* 148, 17–37, Cayley starts with linear equations, uses an array to abbreviate a system of equations, and proceeds to operations on matrices considered as single algebraic quantities. Multiplication corresponds to successive substitutions, and in general the order of multiplication matters.

**Grassmann (1844):** *Die lineale Ausdehnungslehre* offers a different route through extension, independence, and products. Compare his actual language and worked examples before translating it into exterior algebra.

These are distinct, historically situated routes. The current meaning of “matrix” should not be silently projected backward.

## The two indices in a matrix

Let a linear map be `T: V → W`. Choose basis vectors `e₁,e₂` in `V` and `f₁,f₂` in `W`.

Suppose

```text
T(e₁) =  2f₁ + 1f₂
T(e₂) = −1f₁ + 3f₂
```

The standard **column-vector convention** records the output coordinates as *columns*:

```text
                    INPUT
                   e₁   e₂

       OUTPUT   f₁  2   −1
                f₂  1    3
```

Thus

```text
      ┌       ┐
A  =  │ 2  −1 │
      │ 1   3 │
      └       ┘
```

**The +1 and −1 did not switch signs or swap mathematical roles.** The +1 belongs to the image of `e₁` and the −1 to the image of `e₂`. The array lists each image vertically rather than horizontally. Its first column is `(2,1)`; its second is `(−1,3)`.

You *can* put the images in rows instead. Then you would use the transpose and row-vector multiplication conventions throughout. The conventional column arrangement is chosen so that

```text
coordinates(T(v)) = A · coordinates(v)
```

and so composition of maps `S ∘ T` corresponds to matrix product `[S][T]`.

More precisely, with output-coordinate functionals `f¹,f²` defined by `fⁱ(fⱼ)=1` when `i=j` and `0` otherwise:

```text
aᵢⱼ = fⁱ(T(eⱼ)).
```

This formula does not presuppose a rectangular display. One index denotes an input basis vector and the other an output-coordinate measurement.

## Entries depend on choices

Keep the same map and the same output basis, but choose new input basis vectors

```text
e′₁ = e₁ + e₂
e′₂ = e₂.
```

Then

```text
T(e′₁) =  1f₁ + 4f₂
T(e′₂) = −1f₁ + 3f₂
```

and the new matrix is

```text
       ┌       ┐
A′  =  │ 1  −1 │
       │ 4   3 │
       └       ┘
```

The *map* is unchanged. Only its entries changed.

If `Q` contains new input basis vectors in old coordinates and `P` similarly contains new output basis vectors, then `A′ = P⁻¹AQ`. For an endomorphism with the *same* basis change on both sides, `A′ = P⁻¹AP`.

## Similar-looking arrays, different mathematical objects

| Original object | What an entry records | Basis change |
| --- | --- | --- |
| Linear map `T: V → W` | `fⁱ(T(eⱼ))` | `A′ = P⁻¹AQ` |
| Bilinear form `B: V × V → K` | `B(eᵢ,eⱼ)` | `B′ = PᵀBP` |
| System of linear equations | Coefficient in an equation | Row operations and substitutions |
| Data table | Measurement indexed by labels | Depends on interpretation |

We should not assume that a bilinear form and an endomorphism are the same object just because both are written as square arrays.

## Determinant-first and exterior-power interpretations

For `dim V = n`, the top exterior power `ΛⁿV` is one-dimensional. Every endomorphism `T: V → V` induces a map `ΛⁿT` that multiplies by a scalar:

```text
ΛⁿT(e₁ ∧ ⋯ ∧ eₙ) = det(T) (e₁ ∧ ⋯ ∧ eₙ).
```

This gives a basis-independent *modern* construction of determinant. Its interpretation as oriented volume is natural, but is **not** necessarily the historical motivation of Cramer, Sylvester, or Cayley.

More generally, `ΛᵏT` has coefficients that are the `k × k` minors of the matrix of `T`. In this way modern exterior algebra gives a precise interpretation of Sylvester's families of determinants, including minors of rectangular matrices, while leaving the original historical question open.

## Research questions

1. Read Sylvester's 1850 definition beside Cayley's 1858 opening examples. How does the *purpose* of the array change?
2. Before matrix algebra, what operations are performed directly on determinant expressions, minors, coefficients, and substitutions?
3. What exactly did Grassmann's constructions permit without arranging everything into a two-index array?
4. When was the treatment of operators as the basic objects systematically adopted? Identify individual authors and papers rather than assume a single moment.
5. How did the column convention become standard? Find specific early printed examples.
6. What information is invisible in an array without the domain, codomain, and chosen coordinate systems?

## Sources and reading links

- [Sylvester's use of *matrix*, exact 1850 reference and wording (MacTutor)](https://mathshistory.st-andrews.ac.uk/Miller/mathword/m/).
- [History of matrices and determinants (MacTutor)](https://mathshistory.st-andrews.ac.uk/HistTopics/Matrices_and_determinants/).
- [Cayley, *A Memoir on the Theory of Matrices* (1858), original journal record, pp. 17–37](https://www.jstor.org/stable/108649).
- [Cayley original memoir, digitized scan (Wikimedia)](https://upload.wikimedia.org/wikipedia/commons/1/1a/A_Memoir_on_the_Theory_of_Matrices_%28IA_jstor-108649%29.pdf).

**Editorial rule:** Separate original texts and verified historical statements from the explanatory formulas introduced here.
