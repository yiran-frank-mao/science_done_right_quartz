---
created: 2024-08-26
updated: 2024-11-02
completed: true
---
## Jordan Domains

> [!definition] Jordan Path, Jordan Curve, Jordan Arc
> A *Jordan path* is a simple [[Integration and Primitives#^3a89f0|closed path]] $\newcommand{\C}{\mathbb{C}}\gamma\colon[0,1]\to \C$, that is, $γ$ is a closed path which doesn’t cross itself, except at the common endpoints.
> A (piecewise-$C^{1}$) *Jordan curve* $\Gamma⊂\C$ is the [[Relations and Functions#^8f2f00|image]] of a Jordan path, i.e. $\Gamma$ is a Jordan curve if there exists a Jordan path $γ \colon [0,1] \to \C$ such that $\gamma([0,1]) = \Gamma$. Such a $\gamma$ is called a *Jordan parametrization* of $\Gamma$. Specifically, A *Jordan arc* $\Gamma ⊂C$ is the image of an [[Relations and Functions#^042daf|injective]] path $γ \colon [0,1] →\C$.

>[!remark]+ Jordan parametrisations are not unique
> For example, $t\mapsto e^{2\pi i t}$ and $t\mapsto e^{4 \pi i t}$ both parametrize the unit circle $\partial\Delta$.

> [!definition] Jordan Domain
> A *Jordan domain* $D ⊂ \C$ is a domain such that $∂D$ is a [[Construction of Sets#^e08e6f|disjoint union]] of finitely many Jordan curves. ^df720b

>[!remark]+
>Jordan domains can be either bounded or unbounded.

Intuitively, the integral of a holomorphic function around a Jordan curve/arc is independent of the parametrization of the curve up to the sign. This is because we can integrate the function around the curve clockwise or counterclockwise, and the result should be the same in terms of magnitude but opposite in sign.

> [!lemma]
> Let $\Gamma ⊂ \C$ be a Jordan curve or arc. Let $γ$ and $\tilde{\gamma}$ be Jordan parametrisations of $\Gamma$. Then exactly one of the following is true:
> - for all functions $f$ holomorphic in a neighborhood of $\newcommand{\dd}{\:\mathrm{d}}\Gamma$ we have$$\int_\gamma f(z)\dd z=\int_{\tilde{\gamma}}f(z)\dd z$$
> - for all functions $f$ holomorphic in a neighborhood of $\Gamma$ we have$$\int_\gamma f(z)\dd z=-\int_{\tilde{\gamma}}f(z)\dd z$$
> $\quad$

*Proof*  It suffices to just prove the statement for Jordan arcs, as any Jordan curve can be cut into Jordan arcs. So let $\Gamma$ be a Jordan arc. Then either $\gamma(0)=\tilde{\gamma}(0)$ or $\gamma(1)=\tilde{\gamma}(0)$. For case 1, $\gamma$ and $\tilde{\gamma}$ are [[The Homotopy Invariance Theorem#^fc0803|PCE-homotopic]] via $$\Lambda(t,s)=\gamma(st+(1-s)\gamma^{-1}(\tilde{\gamma}(t)))$$Notice that by injectivity, the inverse $\gamma^{-1}$ exists. And $\gamma^{-1}$ is continuous since $[0,1]$ is compact, so $\gamma^{-1}\circ\tilde{\gamma}:[0,1]\to[0,1]$ is continuous as well by [[Continuous Functions on Topological Spaces#^3626d1|the proposition]], leading to the continuity of $\Lambda$. Therefore, by the Homotopy Invariance Theorem, we have $$\int_{\gamma}f(z)\dd z=\int_{\tilde{\gamma}}f(z)\dd z$$The proof for case 2 is by applying case 1 to $\gamma$ and $\tilde{\gamma}^{-}$, and we will get a negative sign eventually. $\square$

>[!remark]+ Integral along a Jordan curve
>Now if $\Gamma$ is a Jordan curve with a chosen orientation, and $f$ is holomorphic in a neighborhood of $\Gamma$, we can now write $\int_{\Gamma}f(z)\dd z$ without ambiguity.

>[!definition] Standard Orientation
>The *standard orientation* of the boundary of a Jordan domain $D$ is the orientation such that the region $D$ is to the left of the curve.
>![standard_orientation.png|200](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/standard_orientation.png)

> [!theorem] Complex Green's Theorem
> $$\int_{\partial D}f\dd{z}=\int_D\left(i\frac{\partial f}{\partial x}-\frac{\partial f}{\partial y}\right)\dd x\dd y$$

> [!theorem] Cauchy Integral Theorem
> Let $D$ be a bounded Jordan domain. If $f ∈ H(\overline{D})$, then $$\int_{\partial D}f(z)\dd z=0$$ ^faa760

> [!comment]+ A picture proof of the Cauchy Integral Theorem
> One intuitive way to understand this theorem is to think of the Jordan domain as indicated in the following figure. We add paths that connect the boundary and holes, then the integral of $f$ around the boundary of the Jordan domain is the the sum of integrals around the blue loop and the red loops. Since $f$ is holomorphic in the region enclosed by the blue loop, the integral around the blue loop is zero. Same for the red loops. Therefore, the integral around the boundary of the Jordan domain is zero.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/jordan_domain_boundary_integral.png" alt="sphere" style="width:45%;">

*Proof*  We evaluate the the integral using Green's theorem: $$\int_{\partial D}f(z)\dd{z}=\int_D\left(i\frac{\partial f}{\partial x}-\frac{\partial f}{\partial y}\right)\dd{x}\dd{y}=2i\int_{D} \frac{\partial f}{\partial \bar{z}}\dd x\dd y=0$$The last step is from [[Complex Differentiability#^754871|condition for complex differentiability]], so $\frac{\partial f}{\partial \bar{z}}=0$. $\square$

>[!remark]+ A result in complex differential geometry
> We actually achieve a result in complex geometry: $$\dd z=\dd x+i\dd y,\quad2i\dd x \dd y=\dd \bar{z} \dd z$$

> [!theorem] Cauchy Integral Formula for Jordan Domains
> Let $D$ be a bounded Jordan domain and let $f ∈H(\overline{D})$. Then for all $z ∈D$, $$f^{(k)}(z)=\frac{k!}{2\pi i}\int_{\partial D}\frac{f(\zeta)}{(\zeta-z)^{k+1}}\dd{\zeta}$$ ^8728b8

*Proof*  Let $z\in D$ and choose $r$ such that $\overline{\Delta(z,r)}\subset D$. Let $\tilde{D}:=D\setminus \overline{\Delta(z,r)}$, which is a Jordan domain with $\partial \tilde{D}=\partial D \sqcup \{|\zeta-z|=r\}$, but importantly the standard orientation on $\{|\zeta-z|=r\}$ is the opposite of that as boundary of  $\Delta(z,r)$. Then $g(\zeta)=\frac{f(\zeta)}{(\zeta-z)^{k+1}}\in H\left(\overline{\tilde{D}}\right)$, so by [[Cauchy Integral Formula for Jordan Domains#^faa760|Cauchy integral theorem]], we have $$\begin{aligned}\text{0}&=\frac{k!}{2\pi i}\int_{\partial\tilde{D}}\frac{f(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta\\&=\frac{k!}{2\pi i}\int_{\partial D}\frac{f(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta-\frac{k!}{2\pi i}\int_{\partial\Delta(z,r)}\frac{f(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta\\&=\frac{k!}{2\pi i}\int_{\partial D}\frac{f(\zeta)}{(\zeta-z)^{k+1}}d\zeta-f^{(k)}(z)\end{aligned}$$where the last equality follows from the [[Cauchy Integral Formula for Disks#^8d28bf|Cauchy integral formula for disks]]. $\square$

> [!comment]+ A new insight on calculating integrals
> This idea where we use the Cauchy integral theorem to reduce the integral around the boundary to an integral around a “problem point” has wide applications in mathematics and physics. Suppose $f$ is holomorphic in a a neighborhood of $\overline{D}\setminus\{a_1,\ldots,a_n\}$. Then choosing $\varepsilon$ small enough, we can cut disks $\Delta(a_i,\varepsilon)$ out of $D$, and get $$\int_{\partial D}f(z)\dd{z}=\sum_{j=1}^n\int_{\partial\Delta(a_j,\epsilon)}f(z)\dd{z}$$
> As an application, if $p(z)$ is a polynomial, and $D$ is a bounded Jordan domain such that none of the roots of $p$ lie on the boundary of $D$, then we can evaluate $$\int_{\partial D}\frac1{p(z)}\dd{z}=\sum_{j=1}^n\int_{|z-\lambda_j|=\epsilon}\frac1{p(z)}\dd{z}$$where $\lambda_j$ are the roots of $p$, and the right hand side can be calculated by Cauchy integral formula.
