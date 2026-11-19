> [!definition] Sesquilinear Form
> On a complex [[Mathematics/Linear Algebra/Vector Spaces#^f4b63e|vector space]] $V$, a *sesquilinear form* is a map $\newcommand{\C}{\mathbb{C}}\varphi\colon V\times V\to \C$ that is linear in the first argument and antilinear in the second argument, i.e. for all $u,v,w,z\in V$ and $\alpha,\beta\in \C$, there holds $$\varphi(\alpha u + v, \beta w+z)=\alpha \overline{\beta} \varphi(u,w)+ \overline{\beta} \varphi(v,w) + \alpha \varphi(u, z) + \varphi(v,z).$$
> Thus it can also be viewed as a bilinear map $V \times \overline{V} \to \C$, thus a linear map $V \times \overline{V} \to \C$ (ref. [[Tensors and Tensor Products#^732917|universal property of vector space tensor products]]). ^concept-06e6cdf0c855

> [!definition] Conjugate of a Sesquilinear Form
> Suppose $\varphi\colon V\times V \to \C$ is a sesquilinear map, then we can define its *conjugate* by $$\overline{\varphi}(z,w)=\overline{\varphi(w,z)}.$$
> If $\varphi = \overline{\varphi}$, then it is called a *Hermitian form*; If $\varphi = -\overline{\varphi}$, then it is called a *skew-Hermitian form*.

> [!proposition]
> Every sesquilinear form can be uniquely decomposed into a sum of a Hermitian form and a skew-Hermitian form. ^5a2a7f

*Proof*
