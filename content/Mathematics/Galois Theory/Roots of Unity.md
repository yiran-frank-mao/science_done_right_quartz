## Cyclotomic Field

> [!definition] Cyclotomic Field
> Let $n$ be a positive integer. The subfield of $\C$ generated over $\Q$ by an $n$-th root of unity $\zeta_{n}=\exp(2\pi i/n)$ is called the $n$-th cyclotomic field, denoted by $\Q(\zeta_{n})$.

> [!proposition]
> Let $p$ be a [[Division and Prime#^47f235|prime]], and let $\zeta_{p}=\exp(2\pi i/p)$. The Galois group of $\Q(\zeta_{p})$ over $\Q$ is a cyclic group of order $p-1$. It is isomorphic to the multiplicative group $\newcommand{\F}{\mathbb{F}}\F_{p}^{\times}$. Futhermore, for any subfield $F$ of $\C$, the Galois group of $F(\zeta_{p})$ over $F$ is a cyclic group.
> 

*Proof*  Let $G$ be the Galois group of $\Q(\zeta_{p})$ over $\Q$. Clearly, $\Q(\zeta_{p})$ is the splitting field of the irreducible cyclotomic polynomial $f(x)=\frac{x^p-1}{x-1}$, so $\Q(\zeta_{p})$ is a Galois extension, and $|G|=[\Q(\zeta_{p}),\Q]=p-1$. Note that $\Q(\zeta_{p})\cong \Q[x]/(f)$, the elements in $G$ are precisely $\Q$-isomorphisms $\Q[x]/(f)\to \Q(\zeta_{p})$, which are maps $\sigma_{i}$ that maps $[x]$ to $\zeta_{p}^{i}$. In $G$, $\sigma_{i}$ will act as an automorphism and send $\zeta_{p}$ to $\zeta_{p}^{i}$. They satisfy $$(\sigma_{i}\circ \sigma_{j})(\zeta_{p})=\zeta_{p}^{ij}=\sigma_{ij},$$thus can be naturally identified with elements in $\F_{p}^{\times}$. Similarly, the element in the Galois group of $F(\zeta_{p})$ over $F$ are of the form, so this Galois group must be a subgroup of $G$, which has to be cyclic. $\square$

<u><b>e.g.</b></u>  Let $p=17$, we have the following diagram of Galois extensions hold:

<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/root_of_unity_example.svg" alt="root_of_unity_example" style="width:40%;"/>

One can see that $G=\{\sigma_{1},\sigma_{4},\sigma_{13},\sigma_{16}\}\cong C_{4}$ is the only subgroup of order 4 in $\Z_{17}^{\times}$ (see [[Cyclic Groups#^937b31|proposition]]). $\Q\left(\zeta_{17}+\zeta_{17}^4+\zeta_{17}^{13}+\zeta_{17}^{16}\right)$ is the fixed field of $G$, because elements in $G$ cyclicly permutes $\zeta_{17}$, $\zeta_{17}^{4}$, $\zeta_{17}^{13}$, $\zeta_{17}^{16}$, and $\zeta_{17}\cdot\zeta_{17}^4\cdot\zeta_{17}^{13}\cdot\zeta_{17}^{16}=1$, the only symmetric expression that is fixed by elements in $G$ is  $\zeta_{17}+\zeta_{17}^4+\zeta_{17}^{13}+\zeta_{17}^{16}$. As $G\cong C_{4}$ is a [[Homomorphisms, Normal Subgroup & Conjugation#^normal|normal subgroup]] of $\Z_{17}^{\times}$, $\Q\left(\zeta_{17}+\zeta_{17}^4+\zeta_{17}^{13}+\zeta_{17}^{16}\right)$ is also a Galois extension over $\Q$, and $H=\Z_{17}^{\times}/G\cong C_{4}$.
In fact, $\zeta_{17}+\zeta_{17}^4+\zeta_{17}^{13}+\zeta_{17}^{16}$ has minimal polynomial $f(x)=x^{4}+x^{3}-6x^{2}-x-1$, whose resolvent polynomial is $$g(x)=x^{3}+2x^{2}-3x-1=(x+1)(x^{2}+x-1)$$with non-square discriminant. This means $H$ has to be either $D_{2}$ or $C_{4}$ according to [[Cubic and Quartic Equations#^ab1d81|the table]]. $H$ is cyclic, so must be $C_{4}$, which verifies our previous arguments.

> [!theorem]
> For any $\zeta_{n}=e^{\frac{2\pi i}{n}}$, $\Q(\zeta_{n})$ has degree $\phi(n)$ over $\Q$, where $\phi(n)$ is the [[Arithmetic Functions#^d3f605|Euler's totient function]].
> 

> [!theorem] Kroncker-Weber Theorem
> Every Galois extension of $\Q$ whose Galois group is abelian is contained in a cyclotomic field $\Q(\zeta_{n})$ for some $n\in\N$.

> [!theorem]
> A number $x \in \C$ is constructible if and only if its Galois group (the Galois group of the splitting field of its minimal polynomial) has order $2^{m}$ for some $m$.
> 

