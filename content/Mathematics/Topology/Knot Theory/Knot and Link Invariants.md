> [!definition] Knot and Link Invariants
> A knot (link) invariant is a function $f$ on the set of knots (links) that is constant on isotopy classes. That is, if $K_1$ and $K_2$ are equivalent up to ambient isotopy, then $f(K_1) = f(K_2)$.

> [!remark]
> It is also true that $f(K_{1})\neq f(K_{2})$ implies $K_{1}\neq K_{2}$, while different knots may have the same invariant.

## Tricolourbility

A knot $K$ is tricolourable if there exists a proper 3-colouring of the knot diagram.


## Jones Polynomial

> [!definition] Jones Polynomial
> The Jones polynomial of a link $J(L)(t)$ is recursively defined as follows:
> - $J(O)=1$ for the unknot $O$;
> - skein relation: $t^{-1}J(L_{+})-tJ(L_{-})=\left(t^{\frac12}-t^{-\frac12}\right)J(L_0)$, where $L_{+}$, $L_{-}$, and $𝐿_{0}$ are three links, which are identical except for some neighbourhood, in which they differ by the crossing changes or smoothing according to the figure below: ![jones_polynomial.svg|400](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/jones_polynomial.svg)
>
> Moreover, a modified Jones polynomial $𝐽(𝐿)(ℎ)$ is obtained from the Jones polynomial by substituting $t=e^{h}$.

## Conway Polynomial

> [!definition] Alexander–Conway Polynomial
> The Conway polynomial associates to each link a polynomial in $𝑧$. Given a link diagram $𝐷$, 𝐶(𝐷) obeys two rules:
> - For the unknot diagram $𝑂$, $𝐶(𝑂)= 1$;
> - $𝐶( )−𝐶( )= 𝑧 \cdot 𝐶( )$

