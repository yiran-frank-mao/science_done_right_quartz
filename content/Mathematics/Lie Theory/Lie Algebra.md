> [!definition] Lie Algebra  
> A Lie algebra over a [[Ring, Field and Integral Domain#^575174|field]] $F$ is a $F$-vector space $E$ endowed with an operation $[\cdot,\cdot] \colon E \times E \to E$ which is linear in each argument, satisfies $[a,a]=0$ for all $a\in E$ and the Jacobi identity:  $$[a, [b,c]] + [b, [c,a]] + [c, [a,b]] = 0 $$for all $a, b, c \in E$. ^5007ba

<u><b>e.g.</b></u>  
- If $M$ is a [[Manifolds and Atlases#^6ef2ef|smooth manifold]], $\mathfrak{X}(M)$ is a Lie algebra.
- If $V$ is a finite dimensional vector space over a field $F$ of dimension $n$, then the space of [[Morphisms#^9a350e|endomorphisms]] $\newcommand{\End}{\mathrm{End}}\End(V)$ (i.e. the set of all linear maps $V\to V$) is a Lie algebra over $F$ with the Lie bracket defined as the commutator: $$[f,g] = f\circ g - g\circ f.$$Only the Jacobi identity needs to be checked: $$\begin{aligned} &([f,[g,h]]+[g,[h,f]]+[h,[f,g]])(v)\\=&\,f\circ [g,h](v)-[g,h]\circ f(v)+g\circ[h,f](v)\\&\,-[h,f]\circ g(v)+h\circ [f,g](v)-[f,g]\circ h(v)\\=&\,fgh(v)-fhg(v)-ghf(v)+hgf(v)+ghf(v)-gfh(v)\\&\,-hfg(v)+fhg(v)+hfg(v)-hgf(v)-fgh(v)+gfh(v)\\=&\,0.\end{aligned}$$To distinguish this Lie algebra from the [[Ring, Field and Integral Domain#^178485|ring]] $(\End(V),\circ)$, we will denote it as $\End(V)_{\mathrm{Lie}}$ or $\mathfrak{gl}(V)$, and call it the general linear Lie algebra of $V$. ^d72504

$\quad$ 
> [!proposition]
> Lie algebra is a non-associative algebra over the field.

*Proof*  Lie bracket gives a multiplication which is compatible with the vector space structure. i.e. Lie bracket is bilinear. $\square$

The concepts of isomorphism and Lie subalgebra are defined in a familiar way:

> [!definition] Isomorphic Lie Algebras
> Two Lie algebras $L$ and $L'$ are said to be isomorphic if there exists a linear bijection $\phi \colon L \to L'$ such that $$\phi([x,y]) = [\phi(x),\phi(y)]$$ for all $x,y\in L$.
> 

> [!definition] Lie Subalgebra
> A Lie subalgebra of a Lie algebra $L$ is a subspace $L' \subseteq L$ such that $[x,y] \in L'$ for all $x,y \in L'$.

