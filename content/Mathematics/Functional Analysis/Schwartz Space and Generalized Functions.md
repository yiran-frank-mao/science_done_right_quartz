## Schwartz Space

> [!definition] Schwartz Space
> For any smooth $\newcommand{\R}{\mathbb{R}}\newcommand{\C}{\mathbb{C}}\newcommand{\N}{\mathbb{N}}f\in C^{\infty}(\R^{n},\C)$, multi-indices $\alpha,\beta\in \N^{n}$, we define its *$\alpha,\beta$-Schwartz* seminorm as 
> $$ \|f\|_{\alpha,\beta} := \sup_{x\in \R^{n}}| x^{\alpha} (\partial^{\beta} f)(x) |, $$
> where $x^{\alpha}=x_{1}^{\alpha_{1}}x_{2}^{\alpha_{2}}\cdots x_{n}^{\alpha_{n}}$ and $\partial^{\beta}=\frac{\partial^{\beta_{1}}}{\partial x_{1}^{\beta_{1}}}\frac{\partial^{\beta_{2}}}{\partial x_{2}^{\beta_{2}}} \cdots \frac{\partial^{\beta_{n}}}{\partial x_{n}^{\beta_{n}}}$.
> The *Schwartz Space* $\newcommand{\S}{\mathcal{S}}\S(\R^{n})$ is then a space of rapidly decreasing functions: 
> $$ \S(\R^{n}):=\{f\in C^{\infty}(\R^{n},\C) \mid \text{for all } \alpha,\beta\in\N^{n}, \|f\|_{\alpha,\beta}<\infty \}. $$
> 

<u><b>e.g.</b></u>
- In $\R^{2}$, the function $f(x,y)=(x^{\alpha_{1}} +y^{\alpha_{2}}) e^{-(x^{2}+y^{2})}$ is in $\S(\R^{2})$ for any multi-index $(\alpha_{1},\alpha_{2})\in \N^{2}$;
- Any compactly supported smooth function is in $\mathcal{S}(\R^{n})$;
$\quad$

> [!proposition]
> $\mathcal{S}(\R^{n})$ is a Fréchet space with the topology induced by the countable family of seminorms $\{\|\cdot\|_{\alpha,\beta}\}_{\alpha,\beta\in \N^{n}}$.
> 

> [!proposition]
> For $1\leq p < \infty$, the Schwartz space $\S(\R^{n})$ is dense in $L^{p}(\R^{n})$.
> 

## Distributions

> [!definition] Tempered Distribution
> A *tempered distribution* is a continuous linear functional on $\S(\R^{n})$. That is, the space of tempered distributions is the dual space $\S'(\R^{n})$ of $\S(\R^{n})$.

Instead of focusing on pointwise values, distributions generalize functions by how it acts on smooth “test functions” via a continuous linear functional. Here are some motivating examples:

<u><b>e.g.</b></u>
- Let $f\colon\R\to \C$ be some integrable polynomially bounded function (i.e., there exists some polynomial $p(x)$ such that $|f(x)|\leq p(x)$ for all $x\in\R$). Then it induces a tempered distribution $\tilde{f}\colon \S(\R)\to \C$ by $$\newcommand{\dd}{\,\mathrm{d}}\tilde{f}(\varphi) = \int_{\R} f(x)\varphi(x)\dd x.$$The integral converges because every $\varphi \in \S(\R)$ decays faster at infinity than any polynomial.
- The familiar Dirac delta from physics is not a classical function but is perfectly defined as a distribution $C^{\infty}_{c}(\R)\to \R$. It “picks out” the value of a test function at zero: $$\delta(\varphi)= \varphi(0).$$More generally, the shifted delta at point $a$ works similarly: $\delta_{a} (\varphi) = \varphi(a)$. In fact, many singular objects in physics (point sources, surface charges, impulsive forces) are rigorously modeled this way as distributions rather than classical functions.
$\quad$

> [!lemma] Continuity Test Lemma
> 


> [!definition] Distribution (Generalized Function)
> A *distribution* or *generalized function* is a continuous (complex or real) linear functional on $C_{c}^{\infty}(U)$ for some open set $\newcommand{\R}{\mathbb{R}}U\subseteq \R^{n}$, where $C_{c}^{\infty}(U)$ is the space of all smooth functions with compact support in $U$, equipped with the usual LF-topology. The space of all distributions on $U$ is denoted by $\mathcal{D}'(U)$.

 The ordinary locally integrable functions can be embedded into the space of distributions by the mapping $$f\mapsto \left(\varphi\mapsto \int_{U} f(x)\varphi(x)\dd x\right),$$where $\dd x$ is the [[Volume Forms#^1e2b6e|volume form]] on $M$. In this way classical functions are identified with a subclass of distributions, often called *regular distributions*.


$\quad$

> [!definition] Smoothing Operator
> A smoothing operator is a continuous linear map $A\colon \mathcal{D}'(U) \to C^{\infty}(U)$.

> [!theorem] Schwartz Kernel Theorem for Scalar Distributions
> Let $U,V\subset \R^{n}$ be open. Then there is a one‑to‑one correspondence between continuous linear maps $T\colon C^{\infty}_{c}(U)\to \mathcal{D}'(V)$ and distributions $K\in \mathcal{D}'(U\times V)$ given by the formula $$ T(\varphi)(\psi) = K(\varphi\otimes \psi),$$for all $\varphi\in C^{\infty}_{c}(U)$ and $\psi\in C^{\infty}_{c}(V)$, where $\varphi\otimes \psi\in C^{\infty}_{c}(U\times V)$ is defined by $$(\varphi\otimes \psi)(x,y):=\varphi(x)\psi(y).$$The distribution $K$ is called the *Schwartz kernel* of $T$.
> 

## Distributional Sections of the Vector Bundle

We can further generalize the idea of distributions to smooth manifolds and vector bundles:

> [!definition] Distributional Section
> Suppose $M$ is a [[Manifolds, Atlases and Smooth Structures#^6ef2ef|smooth manifold]] and $E\to M$ is a finite-rank [[Vector Bundles#^9cb683|vector bundle]]. Let $\Gamma_{c}^{\infty}(M, E^{*})$ be the space of compactly supported smooth sections of the dual bundle, then the space of *distributional sections* of $E$ is defined as the continuous dual $$\mathcal{D}'(M,E):= \Gamma_{c}^{\infty}(M,E^{*})'.$$

> [!theorem] Schwartz Kernel Theorem for Distributional Sections
> Let $M$, $N$ be smooth manifolds, and let $E\to M$, $F\to N$ be smooth finite‑rank vector bundles. Consider the space of compactly supported smooth sections $\Gamma_{c}^{\infty}(M,E)$ with its LF‑topology and the space of distributional sections $\mathcal{D}'(N,F)$. Then every continuous linear operator $T\colon \Gamma_{c}^{\infty}(M,E) \to \mathcal{D}'(N,F)$ is given by a unique distributional kernel $K\in \mathcal{D}'(M\times N, E^{*}\boxtimes F)$ such that for all $\varphi\in \Gamma_{c}^{\infty}(M,E)$ and $\psi\in \Gamma_{c}^{\infty}(N,F^{*})$, we have $$\langle T(\varphi), \psi\rangle = \langle K, \varphi\otimes \psi\rangle,$$where $\varphi\otimes \psi\in \Gamma_{c}^{\infty}(M\times N, E\boxtimes F^{*})$ is defined by $$(\varphi\otimes \psi)(x,y):= \varphi(x)\otimes \psi(y).$$

## The Principle Value

Let us first consider the improper integral $\int^{1}_{-1}\frac{1}{x} \dd x$. This is not well-defined because $1/x$ blows up at $0$. But instead we can do the following: $$\lim_{\varepsilon\to 0^+}\left(\int_{-1}^{-\varepsilon} \frac{1}{x}\dd x+\int_{\varepsilon}^{1} \frac{1}{x}\dd x\right)=0$$This is called the *Cauchy principal value* of the integral. It can be formulated as a distribution:

> [!definition] Cauchy Principle Value
> $\newcommand{\pv}[1]{\mathrm{p.v.}#1}$

For $\varphi\in C^{\infty}_{c}(\R)$, we can define the distribution $\pv{\frac{1}{x}}\in\mathcal{D}'(\R)$ such that $$\pv{\frac{1}{x}}(\varphi)= \lim_{\varepsilon\to 0^{+}} \int_{|x|>\varepsilon} \frac{\varphi(x)}{x}\dd x.$$We shall prove that it is well-defined 


> [!proposition]
> The principal value is the inverse distribution of the function $x\mapsto x$ and is almost the only distribution with this property:
> 
