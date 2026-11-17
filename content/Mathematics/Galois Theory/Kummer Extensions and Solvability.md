## Radical Extensions

> [!definition] Pure Extension & Radical Extension
> A *pure extension* of a field $F$ of type $m$ is a field extension $F(\alpha)/F$ such that $\alpha^{m}\in F$.
> A field extension $K/F$ is called a *radical extension* if there is a tower of intermediate fields $$F=K_{0}\subseteq K_{1} \subseteq \cdots \subseteq K_{n}=K $$
> in which every $K_{i+1}/K_{i}$ is a pure extension. ^concept-d862b90db143

> [!definition] Solvable Polynomials
> Suppose $K$ is the splitting field of $f\in F[x]$. We say that $f$ is *solvable by radicals* if a radical extension is also an extension of $K$.
> 

<u><b>e.g.</b></u>
- Consider $f(x)=x^{n}-1$ over $\newcommand{\Q}{\mathbb{Q}}\Q$. Then the splitting field of $f$ is a [[Mathematics/Galois Theory/Kummer Extensions and Solvability#^concept-d862b90db143|pure extension]];
- Consider $f(x)=x^{3}-2$ over $\Q$. Then the splitting field of $f$ is a radical extension of $\Q$: $$\Q \subset \Q(\sqrt{-3})\subset \Q(\sqrt{-3},\sqrt[3]{2}).$$



## Kummer Theory

> [!theorem] Kummer Extensions
> Let $F$ be a subfield of $\C$ that contains the $p$th root of unity $\zeta_{p}=e^{\frac{2\pi i}{p}}$, where $p$ is a prime number, and let $K/F$ be a Galois extension of degree $p$. Then $K$ is obtained by adjoining a $p$th root. In other words, $K$ is generated over $F$ by an element $\beta$, with $\beta^{p}$ in $F$.
> 



## Quintic Equations

The most famous result in Galois theory is the Abel-Ruffini theorem, which states that there is no general solution in radicals to polynomial equations of degree five or higher.

