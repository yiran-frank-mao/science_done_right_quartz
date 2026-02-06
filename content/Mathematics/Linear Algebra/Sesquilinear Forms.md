> [!definition] Sesquilinear Form
> On a complex [[Vector Spaces#^f4b63e|vector space]] $V$, a *sesquilinear form* is a map $\varphi\colon V\times V\to \C$ that is linear in the first argument and antilinear in the second argument, i.e. for all $u,v,w,z\in V$ and $\alpha,\beta\in \C$, there holds $$\varphi(\alpha u + v, \beta w+z)=\alpha \overline{\beta} \varphi(u,w)+ \overline{\beta} \varphi(v,w) + \alpha \varphi(u, z) + \varphi(v,z).$$
> Thus it can also be viewed as a bilinear map $V \times \overline{V} \to \C$.

> [!definition] Conjugate of a Sesquilinear Form
> Suppose $\varphi\colon V\times V \to \C$ is a sesquilinear map, then we can define its *conjugate* by $$\overline{\varphi}(z,w)=\overline{\varphi(w,z)}.$$
> If $\varphi = \overline{\varphi}$, then it is called *Hermitian*; If $\varphi = -\overline{\varphi}$, then it is called *skew-Hermitian*.

> [!proposition]
> Every sesquilinear form can be uniquely decomposed into a sum of a Hermitian form and a skew-Hermitian form. ^5a2a7f

