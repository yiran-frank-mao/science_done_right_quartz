## The Heisenberg Algebra

> [!definition] Heisenberg (Oscillator) Algebra
> The *Heisenberg algebra* or *Oscillator Algebra* $\newcommand{\vir}{\mathfrak{vir}}\newcommand{\Hei}{\mathfrak{H}}\Hei$ is a [[Complex Numbers#^a81924|complex]] [[Lie Algebra#^5007ba|Lie algebra]] with a basis $\newcommand{\R}{\mathbb{R}}\newcommand{\Z}{\mathbb{Z}}\{\hbar 1_{\Hei}\}\cup\{a_{n}\}_{n\in\Z}$ and Lie bracket defined by $$[\hbar 1_{\Hei}, a_{n}]=0,\quad [a_{m},a_{n}]=m\delta_{m,-n}\hbar 1_{\Hei}.$$
> Here $\hbar$ is the reduced Planck constant, and is often set to $\newcommand{\C}{\mathbb{C}}1\in\C$ in mathematical treatments.

The Heisenberg algebra exists by the following construction:

> [!proposition]
> A [[Central Extensions of Lie Algebras#^c4c058|central extension]] of the abelian algebra of trigonometric polynomials on the circle, i.e., functions $S^{1}\to \C$ with finite Fourier series, forms a Heisenberg algebra through the Lie bracket $$\newcommand{\dd}{\,\mathrm{d}} [f,g]:=\left(\frac{1}{2\pi}\int_{0}^{2\pi}f'(t)g(t)\dd t \right) \cdot z,$$
> where $z$ is a central element.
> 

*Proof*  Let us denote the standard basis elements as $e_{n}=x\mapsto x^{n}$. Then $$[e_{m},e_{n}]=\frac{1}{2\pi}\int_{0}^{2\pi} e^{i(m+n)t}im\dd t \cdot z = im\delta_{m,-n}z.$$Setting $a_{n}\mapsto e_{n}$ and $1_{\Hei}\mapsto z$ gives the desired isomorphism. $\square$

> [!definition] Fock Space Representation of $\Hei$
> Introduce the [[The Fock Space#^ecdf5b|bosonic Fock space]] $\newcommand{\F}{\mathcal{F}}\F=\C[x_{1},x_{2},\dots]$, the space of polynomials in infinitely many variables. Given $\lambda\in\C$, define the representation $(\rho_{\lambda},\F)$ of $\Hei$ through $$\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}\rho_{\lambda}(a_{n})=\varepsilon(n)\pddf{}{x_{n}},\quad \rho_{\lambda}(a_{-n})=f\mapsto \varepsilon(n)^{-1}nx_{n}f,\quad \rho_{\lambda}(a_{0})=\lambda I,\quad \rho_{\lambda}(1_{\Hei})=I, $$for all $n>0$ and some $\varepsilon\colon \Z\to \R$. Usually (and here) we set $\varepsilon(n)=n$ for all $n\in\Z$.
> 

> [!proposition]
> The representation $(\rho_{\lambda},\F)$ is irreducible for all $\lambda\in\R$ and $\varepsilon\colon \Z\to \R$ such that $\varepsilon(n)\neq0$ for all $n\in\Z$.
> 

*Proof*  Any polynomial in $\F$ can be reduced to a constant by applying $\rho_{\lambda}(a_{n})$ for sufficiently large $n$. Hence, every nonzero subrepresentation must contain the constants. By repeatedly applying $\rho_{\lambda}(a_{-n})$​, one generates all other polynomials, showing that the subrepresentation is the entire space $\F$. $\square$

## Oscillator Representation of $\vir$

> [!proposition] $\vir$ Subalgebra in $U(\Hei)$
> In [$U(\Hei)$](Universal%20Enveloping%20Algebra#%5E3bf4c7), we can define a subalgebra $\mathfrak{v}$ which is spanned by $$d_{n}:=\frac{1}{2}\sum_{m\in\Z} \colon a_{n-m}a_{m}\colon$$where $\colon a_{m}a_{n}\colon =a_{m}a_{n}$ if $m\leq n$ and $\colon a_{m}a_{n}\colon =a_{n}a_{m}$ otherwise (this is called the *normal ordering*). 
> Then this subalgebra is isomorphic to the [[Witt Algebra and Virasoro Algebra#^61c2ec|Virasoro algebra]] $\vir$ through the map $\theta\colon \vir \to \mathfrak{v}$, $L_{n}\mapsto d_{n}$ and $\kappa\mapsto 1_{\Hei}$.
> 

> [!definition] Oscillator Representation of $\vir$
> We now define a family of representations $(\varphi_{\lambda,\mu},\F)$ of $\vir$ for $\lambda,\mu\in\C$ by
>  $$\varphi_{\lambda,\mu}(L_{n}):=\frac{1}{2}(\rho_{\lambda}\circ \theta )(L_{n}) + i\mu n \rho_{\lambda}(a_{n}) + \frac{\mu^{2}}{2}\delta_{n,0}I, \quad \varphi_{\lambda,\mu}(\kappa)=I,$$for all $n\in\Z$. This is called the *oscillator representation* of $\vir$.
> 

> [!proposition]
> The operators $\{\varphi_{\lambda,\mu}(L_{n})\}_{n\in\Z}$ satisfy 
> 1. $\varphi_{\lambda,\mu}(L_{0})\cdot 1_{\F} = \frac{1}{2}(\lambda^{2}+\mu^{2})$;
> 2. $[\varphi_{\lambda,\mu}(L_{n}),\varphi_{\lambda,\mu}(L_{m})]=(n-m)\varphi_{\lambda,\mu}(L_{n+m})+\delta_{m,-n}\frac{n^{3}-n}{12}(1+12\mu^{2})I$;
> 3. If $f,g\in\F$ and $x\in \vir$, then $\langle \varphi_{\lambda,\mu}(x)f,g \rangle=\langle f, \varphi_{\bar{\lambda},\bar{\mu}}(x^{*})g \rangle$.
> 
> Therefore $(\varphi_{\lambda,\mu},\F)$ is a highest weight representation of $\vir$ with central charge $1+12\mu^{2}$ and highest weight $\frac{1}{2}(\lambda^{2}+\mu^{2})$. Moreover, it is unitary if $\lambda,\mu\in\R$.
> 

*Proof*
1. $$\begin{aligned}\varphi_{\lambda,\mu}(L_{0})\cdot 1 &= \rho_{\lambda}\left(\frac{1}{2}\sum_{j\in\Z} \colon a_{-j}a_{j}\colon\right)\cdot 1 + \frac{1}{2}\mu^{2}\\&= \sum_{j\in\Z_{\geq_{0}}} \rho_{\lambda}(a_{-j}a_{j}) \cdot 1+ \frac{1}{2}\rho_{\lambda}(a_{0}a_{0})\cdot 1 +  \frac{1}{2}\mu^{2} \\&= \sum_{j\in\Z_{\geq_{0}}}x_{j} n \pddf{}{x_{j}}\cdot 1 + \frac{1}{2}\lambda^{2}+\frac{1}{2}\mu^{2} \\ &= \frac{1}{2}(\lambda^{2}+\mu^{2}).\end{aligned}$$
2. $$\begin{aligned}[][\varphi_{\lambda,\mu}(L_{n}),\varphi_{\lambda,\mu}(L_{m})]&=[\rho_{\lambda}(d_{n}),\rho_{\lambda}(d_{m})]+im\mu[\rho_{\lambda}(d_{n}),\rho_{\lambda}(a_{m})]\\&\quad+in\mu[\rho_{\lambda}(a_{n}),\rho_{\lambda}(d_{m})]-mn\mu^{2}[\rho_{\lambda}(a_{n}),\rho_{\lambda}(a_{m})]\\&= (n-m)\rho_{\lambda}(d_{n+m})+\delta_{m,-n}\frac{n^{3}-n}{12}I\\&\quad+i\mu(n^{2}-m^{2})\rho_{\lambda}(a_{m+n})-mn\mu^{2}n\delta_{m,-n}I\\&=(n-m)\varphi_{\lambda,\mu}(L_{n+m})+\delta_{m,-n}\frac{n^{3}-n}{12}(1+12\mu^{2})I.\end{aligned}$$

$\square$

> [!corollary]
> If $c\geq 1$ and $h\geq(c-1)/24$, then the irreducible highest weight representation $L(h,c)$ of $\vir$ is unitarizable. In general, if $c\geq n$ and $h\geq(c-n)/24$ for some $n\in\Z_{>0}$, then $L(h,c)$ is unitarizable.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/region_c%3E%3Dn%2Ch%3E%3D(c-n)24.svg" alt="https://colab.research.google.com/drive/1VS1hO6PE_BWg3OOqn4JPkUYy8bahirjr?usp=drive_link" style="width:80%;"/>
> 

*Proof*  Since $L(nh,nc)\cong L(h,c)^{\otimes n}$ is unitarizable for all $n\in\Z_{> 0}$, given $nc=c'\geq n$ and $nh=h'\geq (c'-n)/24$, let $\mu=\sqrt{(c'-n)/12n}$ and $\lambda=\sqrt{2h'/n-\mu^{2}}$. Then $\lambda,\mu\in\R$ and $(\varphi_{\lambda,\mu},\F)\cong L(h',c')$ is a unitary highest weight representation of $\vir$ with central charge $nc$ and highest weight $nh$. $\square$

 > [!remark]
 > In fact, the irreducible highest representation $L(h,c)$ is also unitarizable for $c\geq 1$ and $0\leq h<(c-1)/24$, but we do not have an explicit oscillator construction yet. This is still an open problem in mathematics.
>
