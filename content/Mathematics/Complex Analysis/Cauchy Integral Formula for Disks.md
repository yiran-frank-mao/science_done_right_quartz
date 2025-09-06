
## Cauchy Integral Formula

We are going to use the homotopy invariance theorem to prove a fundamental result in the study of holomorphic functions, the Cauchy integral formula, which relates the value of a holomorphic function on the boundary of a domain to the value in the interior. Note that generally a function $f ∈H(D)$ is not defined on the boundary of its domain, so to talk about boundary values of holomorphic functions, we will need our functions to be defined on a slightly bigger set:

> [!definition]
> If $\newcommand{\dd}{\:\mathrm{d}}\newcommand{\C}{\mathbb{C}}D\subset \C$ is a [[Holomorphic and Conformal Maps#^08ef59|domain]], then we write $H(\overline{D})$ for $$\{f\in H(D):\text{there exists }D^{\prime}\supset\overline{D}\text{ and } g\in H(D^{\prime})\text{ such that }g|_D=f.\}$$

<u><b>e.g.</b></u>  $\frac{1}{1-z}\in H(\Delta)$ but $\frac{1}{1-z}\notin H(\overline{D})$. 

> [!theorem] Cauchy Integral Formula for Disks
> Let $f\in H\left(\overline{\Delta(a,r)}\right)$. Then for $z ∈ ∆(a, r)$, $$f(z)=\frac1{2\pi i}\int_{|\zeta-a|=r}\frac{f(\zeta)}{\zeta-z}\dd \zeta.$$ ^80b053

*Proof*  Let $I(\varepsilon):=\frac1{2\pi i}\int_{|\zeta-z|=\varepsilon}\frac{f(\zeta)}{\zeta-z}\dd\zeta$. The path $|\zeta-z|=\varepsilon$ is [[The Homotopy Invariance Theorem#^fc0803|CP-homotopic]] to $|\zeta-a|=r$ via $$\Gamma(t,s)=(1-s)a+sz+((1-s)r+s\epsilon)e^{2\pi it}$$Hence for all $\varepsilon>0$, by the [[The Homotopy Invariance Theorem#^bc41a1|homotopy invariance theorem]] ,we have $$I(\varepsilon)=\frac1{2\pi i}\int_{|\zeta-a|=r}\frac{f(\zeta)}{\zeta-z}\dd\zeta$$We will show that $\lim_{\varepsilon\to 0}I(\varepsilon)=f(z)$, and since $I(\varepsilon)$ actually does not depend on $\varepsilon$, we will get the desired result. Observe that $f(z)=\frac1{2\pi i}\int_{|\zeta-z|=\epsilon}\frac{f(z)}{\zeta-z}\dd\zeta$, hence we have $$\begin{aligned}|I(\epsilon)-f(z)|&=\left|\frac{1}{2\pi i}\int_{|\zeta-z|=\epsilon}\frac{f(\zeta)-f(z)}{\zeta-z}\dd\zeta\right|\\&\leq \frac{1}{2\pi} 2\pi \varepsilon \sup_{|\zeta-z|=\epsilon}\left|\frac{f(\zeta)-f(z)}{\zeta-z}\right|\\&=\sup_{|\zeta-z|=\epsilon}|f(\zeta)-f(z)|\end{aligned}$$Since $f$ is continuous, this goes to $0$ as $\varepsilon\to 0$, so we conclude that $f(z)=I(\varepsilon)$. $\square$

> [!remark]
> The Cauchy integral formula tells us that holomorphic functions are very special: the values in the inside of the disk are determined by the values on the boundary. This is very false if you’re only talking about continuous functions. The single variable analog would be to say that a differentiable function $f \colon [a,b] →\C$ was determined by its values at a and b, which is ridiculous in real analysis. 

<u><b>e.g.</b></u>  For $|z|<1$, we have $$e^z=\frac1{2\pi i}\int_{|\zeta|=1}\frac{e^\zeta}{\zeta-z}\dd\zeta=\frac1{2\pi i}\int_0^{2\pi}\frac{e^{e^{it}}}{e^{it}-z}ie^{it}\dd{t}$$Now if $x\in(-1,1)$ is a [[Number Systems#^5fea5c|real number]], we can finally get $$e^{x}=\frac{1}{2\pi}\int_0^{2\pi}\frac{e^{\cos(t)}\left(\cos(\sin(t))-x\cos(t+\sin(t))\right)}{1+x^2-2x\cos(t)}\dd{t}$$

> [!remark] Complex techniques for real integrals
> This is a fact entirely about real integrals, which does not appear very friendly to real analysis methods. Though this example is somewhat contrived, it demonstrates that complex techniques can be powerful tools for solving problems that, on first glance, have nothing to do with complex analysis. We’ll see more examples and techniques later for evaluating real integrals using complex methods, and these techniques are used heavily in large parts of mathematics and physics.

## Derivatives of Holomorphic Functions

We’ll now use the integral formula to show that if $f ∈H(D)$, then $f'∈H(D)$.

> [!lemma]
> Let $k>0$ be an integer, then there exists a polynomial $p(a,b)$ such that for all $a,b\in \C\setminus\{0\}$ with $a\neq b$, we have $$\frac1{(a-b)^k}-\frac1{a^k}-\frac{kb}{a^{k+1}}=\frac{b^2p(a,b)}{(a-b)^ka^{k+1}}$$

*Proof*  We’ll put the right-hand side over a common denominator $(a−b)^{k}a^{k+1}$ and all of the terms with powers $b^0$ and $b^1$ cancel, leaving just terms with $b^2$ or higher. By binomial theorem, $$(a-b)^k=\sum_{j=0}^k\binom kj(-1)^jb^ja^{k-j}=a^k-kba^{k-1}+b^2q(a,b)$$for some polynomial $q(a,b)$. So we have $$\begin{aligned}\frac1{(a-b)^k}-\frac1{a^k}-\frac{kb}{a^{k+1}}&=\frac{a^{k+1}-a(a-b)^k-kb(a-b)^k}{(a-b)^ka^{k+1}}\\&=\frac{a^{k+1}-a(a^k-kba^{k-1}+b^2q(a,b))-kb(a^k-kba^{k-1}+b^2q(a,b))}{(a-b)^ka^{k+1}}\\&=\frac{b^{2}(-aq(a,b)+k^{2}a^{k-1}-kbq(a,b))}{(a-b)^ka^{k+1}}\end{aligned}$$Hence the lemma is proved, with $p(a,b)=-aq(a,b)+k^{2}a^{k-1}-kbq(a,b)$. $\square$

> [!proposition]
> Let $g\in C(\partial \Delta(a,r))$. Define $f\colon\Delta(a,r)\to\mathbb{C}$ by $$f(z):=\frac1{2\pi i}\int_{|\zeta-a|=r}\frac{g(\zeta)}{\zeta-z}\dd\zeta$$Then $f$ is arbitrarily many times $\C$-differentiable, and $$f^{(k)}(z)=\frac{k!}{2\pi i}\int_{|\zeta-a|=r}\frac{g(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta $$

*Proof*  We prove by induction on $k$. The base case $k=0$ holds automatically by its expression. Assume the result holds for $k-1\geq 0$. Now consider the following expression, applying the above lemma with $a=\zeta-z_{0}$ and $b=\Delta z$: $$\begin{aligned}&\frac{f^{(k-1)}(z_0+\Delta z)-f^{(k-1)}(z_0)}{\Delta z}-\frac{k!}{2\pi i}\int_{|\zeta-a|=r}\frac{g(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta \\
=&  \frac{(k-1)!}{2\pi i\Delta z}\int_{|\zeta-a|=r}g(\zeta)\left(\frac1{(\zeta-z_0-\Delta z)^k}-\frac1{(\zeta-z_0)^k}-\frac{k\Delta z}{(\zeta-z_0)^{k+1}}\right)\dd\zeta \\
=& \frac{(k-1)!}{2\pi i\Delta z}\int_{|\zeta-a|=r}g(\zeta)\left(\frac{(\Delta z)^2p(\zeta-z_0,\Delta z)}{(\zeta-z_0-\Delta z)^k(\zeta-z_0)^{k+1}}\right)\dd\zeta \\
=&\Delta z\left(\frac{(k-1)!}{2\pi i}\int_{|\zeta-a|=r}g(\zeta)\left(\frac{p(\zeta-z_0,\Delta z)}{(\zeta-z_0-\Delta z)^k(\zeta-z_0)^{k+1}}\right)\dd\zeta\right)\end{aligned}$$When $\Delta z$ is sufficiently small, the integrand $(\zeta,\Delta z)\mapsto\frac{p(\zeta-z_0,\Delta z)}{(\zeta-z_0-\Delta z)^k(\zeta-z_0)^{k+1}}$ is bounded by some $M$. Therefore by the [[Integration and Primitives#^3914d2|ML estimate]], the above expression goes to $0$ as $\Delta z\to 0$. Hence by principal of mathematical induction, $f^{(k)}(z)=\frac{k!}{2\pi i}\int_{|\zeta-a|=r}\frac{g(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta$ holds for all $k$. $\square$

> [!corollary]
> Let $f ∈H(\overline{∆(a,r)})$. Then $f$ is infinitely many times $\C$-differentiable on $∆(a,r)$ and for $z ∈∆(a,r)$ $$f^{(k)}(z)=\frac{k!}{2\pi i}\int_{|\zeta-a|=r}\frac{f(\zeta)}{(\zeta-z)^{k+1}}\dd\zeta$$ ^8d28bf

*Proof*  By the above proposition and [[Cauchy Integral Formula for Disks#^80b053|Cauchy integral formula]] on $\Delta(a,r)$, $f$ is arbitrarily many times $\C$-differentiable on $∆(a,r)$. $\square$

> [!corollary]
> Let $D$ be a domain and $f ∈ H(D)$. Then $f^{\prime}∈ H(D)$ and so $f$ is infinitely many times $\C$-differentiable on $D$.

*Proof*  Fix some $z_{0}\in D$. Since $D$ is [[Open and Closed Sets#^e112b1|open]], we can choose some $\Delta(z_{0},r)\subset D$, then $\overline{\Delta(z_{0},\frac{r}{2})}\subset D$. We apply the above corollary to get $f$ is infinitely many times $\C$-differentiable on $\Delta(z_{0},\frac{r}{2})$, in particular $\C$-differentiable at $z_{0}$. Since $z_{0}\in D$ is arbitrary, $f$ is infinitely many times $\C$-differentiable on $D$. $\square$