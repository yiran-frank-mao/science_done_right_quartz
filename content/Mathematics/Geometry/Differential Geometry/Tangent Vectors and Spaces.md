---
created: 2024-07-25
updated: 2025-05-03
---
## Definition by Tangent Curves

>[!definition] Tangent Curve
>Fix an $n$-manifold $M$ and a point $\newcommand{\(}{\left(}\newcommand{\)}{\right)}\newcommand{\d}{\mathrm{d}}\renewcommand{\{ }{\left\{ } \renewcommand{\}}{\right\}} \newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}} p \in M$. A tangent curve based at $p\in M$ is a smooth map $\gamma \colon I \to M$ sending $0 \mapsto p$, where $\newcommand{\R}{\mathbb{R}}I \subseteq \R$ is an open neighbourhood of $0$.

>[!definition] First Order Agreement
>On an $n$-manifold $M$, two tangent curves $\gamma_{1}$ and $\gamma_{2}$ based at $p$ are said to agree to first order if there exists a chart $\varphi$ around $p$ such that $$(\varphi\circ \gamma_{1})^{\prime}(0)=(\varphi\circ \gamma_{2})^{\prime}(0)$$We write $\pi_{p}^{\varphi}$ for the map $\gamma \mapsto (\varphi\circ\gamma)^{\prime}(0)$.

>[!lemma]
>If $\gamma_{1}$ and $\gamma_{2}$ satisfy $\pi_{p}^{\varphi}(\gamma_{1})=\pi_{p}^{\varphi}(\gamma_{2})$, that is they agree to first order, then $\gamma_{1}$ and $\gamma_{2}$ agree to first order in any chart around $p$.

*Proof*  Suppose $(\varphi\circ \gamma_{1})^{\prime}(0)=(\varphi\circ \gamma_{2})^{\prime}(0)$, then for any chart $\psi$, we have$$\begin{aligned}(\psi\circ\gamma_{1})^{\prime}(0)&=\psi^{\prime}(\gamma_{1}(0))\cdot \gamma_{1}^\prime(0)\\&=\psi^{\prime}(\gamma_{1}(0))\cdot \left( \varphi^{\prime}(\gamma_{1}(0)) \right)^{-1} \varphi^{\prime}(\gamma_{1}(0))\cdot \gamma_{1}^\prime(0) \\&=\psi^{\prime}(\gamma_{2}(0))\cdot \gamma_{2}^\prime(0)\\&=(\psi\circ \gamma_{2})^{\prime}(0)\end{aligned}$$ $\square$

>[!corollary]
> Agreement to first order is an [[Relations and Functions#^14741d|equivalence relation]].

*Proof*  Clear enough as '$=$' is an equivalence relation. $\square$

> [!definition] Smooth Path Space
> The smooth path space to some manifold $M$ at point $p$, denoted $C_{p}M$, is the set of all tangent curves based at $p$ modulo the equivalence relation of first order agreement: $$\{ \gamma : \gamma \text{ is a tangent curve at } p \} / \sim$$And we introduce the vector operations on $M_{p}$ by selecting a chart $\varphi\colon U\to \R^{n}$ around $p$, and define $\pi_{p}^{\varphi}\colon C_{p}M\to \R^{n},[\gamma]\mapsto(\varphi\circ \gamma)^{\prime}(0)$. Clearly $\pi_{p}^{\varphi}$ is a bijection, and now we can define the vector space operations on $M_{p}$ by $$[\gamma_{1}]+[\gamma_{2}]:=\left(\pi_{p}^{\varphi}\right)^{-1}(\pi_{p}^{\varphi}([\gamma_{1}])+\pi_{p}^{\varphi}([\gamma_{2}]))$$

## Definition by Vectors in $\R^{n}$

> [!definition] Tangent Space
> For $x ∈ M$ we define $T_{x}M$ to be the set of pairs $(\varphi,u)$ where $\varphi\colon U\to V$ is a chart in the atlas for $M$ with $x∈ U$, and $u$ is an element of $\R^{n}$, modulo the equivalence relation which identifies a pair $(\varphi,u)$ with a pair $(\eta,w)$ if and only if $u$ maps to $w$ under the derivative of the transition map between the two charts: $$\d_{\varphi(x)}\left(\eta\circ\varphi^{-1}\right)(u)=w.$$
> We denote such an equivalence class by $[\varphi, u]$. ^76649d

> [!remark]+
> We think of a vector as being an ‘arrow’ telling us which way to move inside the manifold. This information on which way to move is encoded by viewing the motion through a chart $\varphi$, and seeing which way we move ‘downstairs’ in the chart (this corresponds to a vector in $\R^{n}$ according to the usual notion of a velocity vector). The equivalence relation just removes the ambiguity of a choice of chart through which to follow the motion.

> [!definition]
> $$\mathcal{F}_{x}:=\left\{(U,f)\mid \text{open } U\supset\{x\}, f\colon U\to \R \text{ is smooth} \right\}$$


## Definition by Smooth Functions

> [!definition] Derivation Space
> Denote $C^\infty(p)$ as the set of real smooth functions whose domain includes some open neighborhood of $p$. A derivation $\chi$ at a point $p\in M$ is a map $\chi\colon C^{\infty}(p)\to \R$ satisfying for all $\alpha,\beta\in \R$ and $f,g\in C^\infty(p)$ the two conditions: $$\begin{aligned}\chi(\alpha f+\beta g)& = \alpha \chi_(f)+\beta \chi(g)\quad&\text{(linearity)}\\ \chi(fg)&=(\chi (f))g(p)+f(p)(\chi (g))\quad&\text{(Leibniz rule)}\end{aligned}$$
> And we define $D_{x}M$ to be the set of all derivations at $p\in M$. ^f956d2

> [!remark]+ Derivations are directional derivatives
> The archetypal example of a derivation is the directional derivative of a function along a curve: Given a smooth path $\gamma\colon I\to M$ with $\gamma(0) = x$, we can define $$\chi(f)= \left. \frac{\d}{\d t} (f\circ \gamma) \right|_{t=0}$$ Indeed, all derivations are of this form.

> [!theorem] Three Definitions of Tangent Space are Equivalent
> There are isomorphisms between the three spaces $C_{x}M$, $T_{x}M$ and $D_{x}M$.

*Proof*  We will only show $C_{p} M \cong D_{x}M$ here. Define $\Phi\colon C_{p}M \to D_{x}M$ by $$\newcommand{\d}{\mathrm{d}}\newcommand{\ddtz}{\frac{\d}{\d t}\bigg|_{t=0}}\Phi([\gamma])(f):=\ddtz f\circ \gamma.$$That is well-defined. For any $\gamma_{1} \sim \gamma_{2}$, pick a local chart $\varphi$ around $p$, then $$\ddtz f\circ \gamma_{1}=\ddtz (f\circ \varphi^{-1}) \circ (\varphi\circ \gamma_{1})=\nabla(f\circ \varphi^{-1})(\varphi(p)) \cdot (\varphi\circ \gamma_{1})'(0).$$Similarly, $\ddtz f\circ \gamma_{2}=\nabla(f\circ \varphi^{-1})(\varphi(p)) \cdot (\varphi\circ \gamma_{2})'(0)$. As $\gamma_{1} \sim \gamma_{2}$, $(\varphi\circ \gamma_{1})'(0)=(\varphi\circ \gamma_{2})'(0)$, so $$\ddtz f\circ \gamma_{1} = \ddtz f\circ \gamma_{2}.$$Now we check $\Phi([\gamma])$ is a derivation. Clearly, it is linear because derivative is linear. It remains checking the Leibniz rule: $$\begin{aligned}\Phi([\gamma])(fg)&= \ddtz fg \circ \gamma \\ &= \ddtz(f\circ \gamma)(g\circ \gamma)\\&= \left(\ddtz (f\circ \gamma) \right) (g\circ \gamma) + (f\circ \gamma) \left( \ddtz g\circ \gamma \right). \end{aligned}$$Hence $\Phi([\gamma])$ is a well-defined derivation.
Now we show injectivity. Suppose $\Phi([\gamma_{1}])=\Phi([\gamma_{2}])$. Then $$\ddtz f\circ \gamma_{1}=\ddtz f\circ \gamma_{2} \quad\text{for all } f.$$Suppose $\varphi$ is a chart around $p$. Let $\varphi^{i}$ be the $i$th coordinate of $\varphi$. Then $$\ddtz \varphi^{i}\circ \gamma_{1} = \ddtz \varphi^{i}\circ \gamma_{2} \quad \text{for all }i.$$Therefore, $\ddtz \varphi\circ \gamma_{1}=\ddtz \varphi\circ \gamma_{2}$. So $\gamma_{1} \sim \gamma_{2}$.
Finally, we check surjectivity. Suppose $\chi \in D_{x}M$ is a derivation. Fix a chart $\varphi$ near $p$. Without loss of generality, assume that $\varphi(p)=0$. Define a curve $$\gamma(t)=\varphi^{-1}\left(t \cdot \chi(\varphi^{1}), t \cdot x\left(\varphi^{2}\right), \dots, t \cdot x\left(\varphi^{n}\right)\right).$$Note that $$\begin{aligned} \Phi([\gamma])(f)&= \ddtz f \cdot \varphi^{-1}\left(t \cdot \chi(\varphi^{1}), \dots\right) \\ &=\sum_{i=1}^{n} \frac{\partial\left(f \cdot \varphi^{-1}\right)}{\partial \varphi^{i}} \cdot \chi\left(\varphi^{i}\right). \end{aligned}$$$f \cdot \varphi^{-1}$ is a smooth function on a neighborhood of $0\in\R^{n}$. So we can apply Taylor's theorem with remainder to the function $s \mapsto\left(f \cdot \varphi^{-1}\right)(s \cdot y)$ for any fixed $y$ near $0$: $$\newcommand{\dd}{\,\mathrm{d}} \left(f \circ \varphi^{-1}\right)(y)=\left(f \circ \varphi^{-1}\right)(0)+\sum_{i=1}^{n} \frac{\partial\left(f \circ \varphi^{-1}\right)}{\partial \varphi^{i}} y^{i}+\int_{0}^{1} (1-s) \sum_{i,j=1}^{n} y^{i} y^{j} \frac{\partial^{2}\left(f \circ \varphi^{-1}\right)}{\partial \varphi^{i} \circ \varphi^{j}} \dd s.$$Suppose $\varphi^{-1}(y)=q \in M$ near base point $p$. Then the above equation becomes $$f(q)=f(p)+\sum_{i=1}^{n} \frac{\partial\left(f \circ \varphi^{-1}\right)}{\partial \varphi^{i}} \cdot \varphi^{i}(q)+\sum_{i,j=1}^{n} \varphi^{i}(q) \varphi^{j}(q) \int_{0}^{1} (1-s)\frac{\partial^{2}\left(f \circ \varphi^{-1}\right)}{\partial \varphi^{i}\partial \varphi^{j}} \dd s.$$This gives a linearized formula for $f$. Note that both $\varphi^{i}$ and $\varphi^{j}$ vanish at $p$, applying a derivation makes it zero, so $$\chi(f)=\chi\left(\sum_{i=1}^{n} \frac{\partial\left(f \circ \varphi^{-1}\right)}{\partial \varphi^{i}} \varphi^{i}\right)=\sum_{i=1}^{n} \frac{\partial\left(f \circ \varphi^{-1}\right)}{\partial \varphi^{i}} \chi\left(\varphi^{i}\right)=\Phi([\gamma])(f).$$as desired.  $\square$

> [!remark]
> These are three characterizations of the tangent space to a manifold at a point. From now on, we will use the notation $T_{x}M$ to denote the tangent space at $x\in M$, and treat each vector in $T_{x}M$ as whatever definition is most convenient.

> [!proposition]
> Suppose $M$ is a smooth $n$-manifold. The tangent space $T_{x}M$ has dimension $n$ for all $x\in M$.

*Proof*  It suffices to show that the differential of a local chart $\varphi$ is a linear isomorphism between $T_{x}M$ and $\R^{n}$. We have $$\d_{x}\varphi\colon T_{x}M\to \R^{n},[\gamma]\mapsto (\varphi\circ \gamma)^{\prime}(0)$$The map $\d_{x}\varphi$ is a bijection since the derivative of a diffeomorphism is an invertible linear map.  $\square$

> [!proposition] Standard Basis of Tangent Space
> Now suppose the chart $\varphi=(x^{1},x^{2},\dots x^{n})$ around $p\in M$ is given. Then one can define an ordered basis for $T_{p}M$ as derivations: $$\{\frac{\partial}{\partial x^{1}},\frac{\partial}{\partial x^{2}},\dots,\frac{\partial}{\partial x^{n}}\}$$ where each partial derivative operator (at $p$) is defined as $$\pddf{f}{x^{i}}(p):= \left. \pddf{(f\circ \varphi^{-1})}{x^{i}} \right|_{\varphi(p)}.$$

*Proof*  Since we know the tangent space has dimension $n$, it suffices to check the linear independence of the above vectors. Suppose $\sum_{i=1}^{n}a_{i}\pddf{}{x^{i}}=0$. That is, for every smooth function $f$, we have $$\sum_{i=1}^{n}a_{i}\pddf{f}{x^{i}}(p)=\left. \sum_{i=1}^{n}a_{i}\pddf{(f\circ \varphi^{-1})}{x^{i}}\right|_{\varphi(p)} =  0.$$We can choose $f$ so that $f\circ\varphi^{-1}$ is the coordinate function $x^{j}$, and we get $$\sum_{i=1}^{n}a_{i}\delta_{i}^{j}=a_{j}=0.$$ Thus $a_{j}=0$ for all $j$, and the vectors are linearly independent. $\square$

## The Differential of a Smooth Function

> [!definition] Differential
> Let $f\colon M\to \R$ be a smooth function. Then we define the *differential* $\d_{x}f\colon T_{x}M\to\R$ of $f$ at point $x\in M$ to the linear function on $T_{x}M$ given by $$\(\d_{x}f\)(v):=v(f)$$ In general, the differential of a smooth map $F\colon M\to N$ between two manifolds at $x\in M$, written $\d_{x}F\colon T_{x}M\to T_{F(x)}N$ is defined as
> 1. For the tangent curve definition, $\d_{x}F([\gamma])=[F\circ \gamma]$.
> 2. For the chart definition, $\d_{x}F([\varphi,u])=[\psi, \d_{x}(\psi\circ F\circ \varphi^{-1})]$.
> 3. For the derivation definition, $\d_{x}F(v)(f)=v(f\circ F)$.
> $\quad$ ^c1b44c

We shall check that the above is well-defined, and all three definitions are equivalent:

## Tangent Bundle

>[!definition] Tangent Bundle
>A tangent bundle is the [[Construction of Sets#^e08e6f|disjoint union]] of the tangent spaces of a manifold $M$: $$TM= \bigsqcup_{p}T_{p}M=\{(p,v):p\in M, v\in T_p(M)\}$$ ^e3492e

<u><b>e.g.</b></u>  Consider $\R^{n}$, take the global chart $\varphi=\operatorname{id}$. Then $$T\R^{n}=\bigsqcup_{x\in\R^{n}} T_{x}\R^{n} = \R^{n}\times \R^{n}$$

> [!proposition] Smooth Structure on Tangent Bundle
> Given a smooth $n$-manifold $M$, with an atlas $\mathcal{A}=\{\varphi_{\alpha}\colon U_{\alpha}\to V_{\alpha}\subset \R^{n} \}$. Then $TM$ has a canonical structure of dimension $2n$ with its atlas given by $$\tilde{\mathcal{A}}=\{\tilde{\varphi}_{\alpha}=\d \varphi_{\alpha}\colon TU_{\alpha}\to TV_{\alpha},(x,v)\mapsto (\varphi_{\alpha}(x),\d_{x}\varphi_{\alpha}(v))\}$$
>

*Proof*  The above construction gives a unique topology on $TM$ such that the projection $\pi\colon TM\to M$ is continuous. Now we check the coordinate change is diffeomorphism. Consider $$\tilde{\varphi}_{\alpha}\circ \tilde{\varphi}_{\beta}=\(\varphi_{\alpha}\circ\varphi_{\beta}^{-1},  \d_{x}\varphi_{\alpha}\circ \d_{x}\varphi_{\beta}^{-1}\),$$ is a composition of diffeomorphisms, thus a diffeomorphism. $\square$

<u><b>e.g.</b></u>  $TS^{2}=\{(x,v) \in \R^{3} \times \R^{3} \mid \|x\|=1,  x\cdot v=0\}$ is a smooth submanifold of $\R^{6}$.

> [!proposition]
> $TM$ is a [[Vector Bundles#^9cb683|vector bundle]] over $M$.

*Proof*  The bundle projection is the map $\pi\colon TM \to M$ defined by $\pi(p,v)=p$. Clearly $\pi^{-1}(\{p\})=T_{p}M$. The local trivialization is given by the differential of the chart $\varphi\colon U\to \R^{n}$, say, $$\d\varphi \colon TU \to T\R^{n} \cong \R^{n} \times  \R^{n}.$$It is easy to see that $\d\varphi\bigg|_{\pi^{-1}(\{p\})}=\d_{p}\varphi$ is a linear isomorphism onto $\{p\}\times \R^{n}$. $\square$ 


## References and Useful Resources
- [Intrinsic Geometry vs Extrinsic Geometry](https://www.youtube.com/watch?v=VHkL5HpL0HY&list=PLJHszsWbB6hpk5h8lSfBkVrpjsqvUGTCx&index=7)
