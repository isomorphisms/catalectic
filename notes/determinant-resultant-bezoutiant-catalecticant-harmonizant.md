# Determinant, resultant, Bézoutiant, catalecticant, harmonizant

## Where the list came from

Richard Borcherds, *Math 256A / Algebraic Geometry* lecture notes, p. 31 of the [Berkeley PDF](https://math.berkeley.edu/~reb/courses/256A/256A.pdf#page=31), names the **Bézoutiant, catalecticant, determinant, harmonizant, canonizant** immediately after explaining the **resultant** via the Sylvester matrix.

These names do **not** all designate invariants of one linear operator. They arise from different algebraic objects and transformation laws. This is why classical invariant theory is the proper context for the repository.

## A first comparison

| Construction | Starting mathematical objects | Formula or construction | What a vanishing condition means |
| --- | --- | --- | --- |
| **Determinant** | Endomorphism (or square coefficient array with bases understood) | The scalar induced by `ΛⁿT` on `ΛⁿV` | The endomorphism is not invertible |
| **Resultant** | Two homogeneous binary forms (or fixed-degree univariate polynomials) | Determinant of a Sylvester coefficient matrix | A common nonzero projective root, over an algebraic closure |
| **Bézoutiant / Bézoutian** | Two univariate polynomials | `(f(x)g(y) − f(y)g(x))/(x−y)` | The associated Bézout matrix becomes singular when the relevant resultant vanishes (subject to degree conventions) |
| **Catalecticant** | A homogeneous form, notably a binary form of even degree | Determinant of a middle apolarity/contraction map | The middle apolarity map has deficient rank, giving a necessary condition for an unusually short sum-of-powers decomposition |
| **Harmonizant** | A degree-`d` form and a *dual* form of matching degree | Their natural bilinear pairing, expressed as full differential contraction | The two forms are **apolar** |

The determinant is a general construction; a resultant or catalecticant is often *computed using* a determinant. The harmonizant is instead a bilinear invariant (of a pair in dual representations). Calling all of these 'determinants' would erase the objects whose properties they study.

## Example 1: the resultant and the Bézoutiant

Take two linear polynomials:

```text
f(x) = x − a
g(x) = x − b
```

Their resultant is `a − b`, and it vanishes exactly when `a = b` and the two roots coincide.

The Bézoutian expression is

```text
       (x−a)(y−b) − (y−a)(x−b)
B(x,y) = ───────────────────────── = a−b.
                    x−y
```

Thus the Bézout matrix is the `1×1` array `[a−b]`. Its determinant reproduces the resultant in this example.

For higher degrees, expand

```text
B(x,y) = Σᵢⱼ bᵢⱼ xⁱ yʲ.
```

The symmetric coefficient array `(bᵢⱼ)` is the Bézout matrix. The determinant agrees with the standard resultant up to conventional signs and possible degree/leading-coefficient factors; pin the exact conventions before asserting an equality.

The key point: the **resultant is intrinsically an elimination condition**, while the Sylvester matrix and Bézout matrix are two different coefficient constructions for computing it.

## Example 2: a binary quartic and its catalecticant

Write a quartic using binomial-coefficient normalization:

```text
f(x,y) = a x⁴ + 4b x³y + 6c x²y² + 4d xy³ + e y⁴.
```

Its middle catalecticant is

```text
          │ a  b  c │
Cat(f) =  │ b  c  d │ .
          │ c  d  e │
```

The vertical bars denote the **determinant**. The matrix is a symmetric, Hankel-type coefficient matrix, not an arbitrary `3×3` array.

Why those entries? The quartic defines an apolarity map

```text
Sym²(V) → Sym²(V*)
ψ       ↦  Dψ(f)
```

whose matrix (with consistent divided-power/monomial normalization) is the displayed Hankel array. The catalecticant vanishes exactly when this linear map is singular.

If `f = ℓ₁⁴ + ℓ₂⁴`, the map has rank at most two, so `Cat(f)=0`. Be careful with the converse: `Cat(f)=0` is a determinantal condition describing **border rank** ≤2 over an algebraically closed field; an exact decomposition as two fourth powers can need additional hypotheses.

For a change of binary variables `g∈GL₂`, the quartic catalecticant transforms as

```text
Cat(f ∘ g) = det(g)⁶ Cat(f).
```

Hence it is an invariant under `SL₂` and a **relative invariant** under `GL₂`. Its zero locus is preserved under either group.

## Example 3: the harmonizant is a pairing, not a determinant

Let `f ∈ Symᵈ(V*)` be a homogeneous polynomial, and let `ψ ∈ Symᵈ(V)` be a homogeneous element in dual variables, regarded as a degree-`d` constant-coefficient differential operator.

```text
H(f, ψ) = Dψ(f) ∈ F.
```

This is bilinear. Under corresponding *contragredient* changes of basis for the form and dual form, the scalar pairing is unchanged.

The condition

```text
H(f,ψ)=0
```

is **apolarity**.

Dolgachev, *Classical Algebraic Geometry: A Modern View*, [historical notes, p. 75](https://mathweb.ucsd.edu/~eizadi/207A-14/CAG.pdf#page=87), identifies the historical *harmonizant* with this simultaneous bilinear invariant and its vanishing condition. It is connected to the differential contraction used in catalecticant maps.

## A sixth name: canonizant

Borcherds's sentence also mentions **canonizant**. For odd-degree binary forms, this is a *covariant form* associated with canonical sum-of-powers representations. It can be built as a determinant involving linear combinations of adjacent coefficients (the catalecticant of a derived form). This needs its own worked example, and should not be described merely as 'another invariant scalar.'

## Why these belong together

1. **Object:** specify a matrix, pair of forms, single homogeneous form, or form–dual-form pair.
2. **Action:** specify simultaneous substitution, similarity, left/right matrix equivalence, or dual/contragredient action.
3. **Construction:** specify elimination, contraction, determinant, or a covariant.
4. **Transformation law:** distinguish invariant, relative invariant, and covariant.
5. **Geometry:** interpret the zero set: singular maps, intersecting zero loci, deficient apolarity rank, or apolar pairs.

A formula in coefficients is not 'intrinsically invariant' until the transformation law is given.

## References

- [Richard Borcherds, Math 256A notes, p. 31](https://math.berkeley.edu/~reb/courses/256A/256A.pdf#page=31) — originating list and resultant.
- [Igor Dolgachev, *Classical Algebraic Geometry*, p. 75 (PDF page 87)](https://mathweb.ucsd.edu/~eizadi/207A-14/CAG.pdf#page=87) — historical harmonizant and apolarity.
- [Igor Dolgachev, newer chapter on catalecticants](https://dept.math.lsa.umich.edu/~idolga/CAG-1.pdf) — apolarity maps and rank.
- [Karen Hunger Parshall, 'Telling the Life of a Mathematician: The Case of J. J. Sylvester'](https://www.numdam.org/item/RHM_1999__5_2_285_0.pdf) — quartic catalecticant, Sylvester, Cayley.
- [Catalecticant transformation law, with proof (MathOverflow)](https://mathoverflow.net/questions/281217/why-is-the-catalecticant-invariant-under-coordinate-changes).
- [Bézout matrix](https://en.wikipedia.org/wiki/B%C3%A9zout_matrix) — coefficient construction and normalization.
