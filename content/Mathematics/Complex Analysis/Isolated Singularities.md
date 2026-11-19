---
created: 2024-10-04
updated: 2024-10-23
completed: true
---
## Isolated Singularities

> [!definition] Isolated Singularities
> If $f\in H(D)$ and $a\notin D$, but $\Delta(a,0,r)\subset D$ for some $r>0$, then $a$ is called an isolated singularity of $f$.

 <u><b>e.g.</b></u>  $z\mapsto \frac{1}{\sin(1/z)}$ has isolated singularities at $\frac{1}{k\pi}$ for $k\in \Z\setminus\{0\}$, and $0$ is not an isolated singularly.

> [!corollary]
> Suppose $f\in H(D)$, and $a$ is an isolated singularity of $f$. Then we can form the Laurent expansion: $$f(z)=\sum_{n=-\infty}^\infty c_n(z-a)^n$$converging on any $∆(a,0,r) ⊂D$.

*Proof*  Since $a$ is an isolated singularity, there is some $r>0$ such that $\Delta(a,0,r)\subset D$. Then $f\in H(\Delta(a,0,r))$, so we can apply the Laurent expansion theorem.

> [!definition] Removable Singularity, Pole, Essential Singularity
> Suppose $f ∈H(D)$ has an isolated singularity $a$, with Laurent expansion $\sum_{n=-\infty}^\infty c_n(z-a)^n$. Then the singularity is called
> - removable singularity, if $c_n=0$ for all $n<0$.
> - pole, if $c_{n}\neq 0$ for a nonempty finite set of $n<0$.
> - essential singularity, if $c_{n}\neq 0$ for infinitely many $n<0$.
>
> The series $\sum_{n=-\infty}^{-1}c_n(z-a)^n$ is called the principal part of the Laurent expansion. ^451c12

## Characterise Removable Singularities

> [!theorem] Characterization of Removable Singularities
> Let $f ∈H(D)$, and suppose that $f$ has an isolated singularity $a$. Then the following are equivalent.
> 1. $f$ has a removable singularity at $a$.
> 2. $f$ has a holomorphic extension to $D\cup\{a\}$.
> 3. $\lim_{z\to a}f(z)$ exists.
> 4. $f$ is bounded on some $\Delta(a,0,\epsilon)$.
> $\quad$

*Proof*  $1)⇒2)$: If $f$ has a removable singularity at $a$, then $f$ has a Laurent expansion $f(z)=\sum_{n=-\infty}^\infty c_n(z-a)^n$ with $c_n=0$ for all $n<0$. That is, $f(z)=\sum_{n=0}^\infty c_n(z-a)^n$, which is a [[Series of Complex Functions#^4e8565|power series]], converging normally on some disk $\Delta(a,r)$ to a holomorphic function $h\in H(\Delta(a,r))$. Clearly $h$ agrees with $f$ on $\Delta(a,0,r)$. Then we define $g\colon D\cup\{a\} \to \C$ by$$g(z)=\begin{cases}f(z)&z\neq a\\q(a)&z=a\end{cases}$$Then $g$ is [[Complex Differentiability#^44f14c|complex differentiable]] on $D$ since it agrees with $f$ in a neighborhood of any $z ∈D$, and is $\C$-differentiable at $a$ since it agrees with $h$ on $\Delta(a,r)$. Therefore $g\in H(D\cup\{a\})$, as required.
$2)⇒3)$: The holomorphic extension $g$ is continuous at $a$, so $\lim_{z\to a}f(z)=g(a)$.
$3)⇒4)$: If $\lim_{z\to a}f(z)$ exists, then $f$ is bounded on a neighborhood of $a$, thus bounded on some $\Delta(a,0,\epsilon)$. This can be rigorously showed by $\varepsilon$-$\delta$ argument.
$4)⇒1)$: Suppose $|f(z)|<M$ on $\Delta(a,0,\epsilon)$, and $\sum_{n=-\infty}^\infty c_{n}(z-a)^{n}$ is the Laurent series. Fix some $n<0$, for any $0<\rho<\epsilon$, by [[Integration and Primitives#^3914d2|ML estimate]], we have$$\begin{aligned}|c_n|&=\left|\frac1{2\pi i}\int_{|\zeta-a|=\rho}\frac{f(\zeta)}{(\zeta-a)^{n+1}}\dd\zeta\right|\\&\leq\frac1{2\pi}\cdot2\pi\rho\cdot\sup_{|\zeta-a|=\rho}\frac{|f(\zeta)|}{\left|\zeta-a\right|^{n+1}}\\&\leq\rho\cdot\frac M{\rho^{n+1}}=\frac M{\rho^n}\end{aligned}$$As it holds for all $0<\rho<\epsilon$, note that $n<0$, we can take $\rho\to 0$ to get $c_n=0$. Therefore the singularity is removable. $\square$

## Characterise Poles and Zeroes

> [!lemma]
> Let $D$ be a domain, $f\in H(D)$, and $f\neq 0$. Suppose either $a\in D$ or $a$ is a pole of $f$. Then there is a unique $N\in\Z$ and $g\in H(D\cup\{a\})$ such that $f(z)=(z-a)^{N}g(z)$ for all $z\in D$ and $g(a)\neq 0$. ^183f67

*Proof*  First consider existence. Suppose $(c_{n})$ are coefficients of the Laurent series of $f$ centered at $a$. Since $f\neq 0$, there is a smallest $N\in\Z$ such that $c_{N}\neq 0$. i.e. $$N:=\min\{n\in\Z\mid c_{n}\neq 0\}$$So we can write $f(z)=(z-a)^{N}\sum_{n=0}^\infty c_{n+N}(z-a)^{n}$. Notice that $\sum_{n=0}^{\infty}c_{n+N}(z-a)^{n}$ converges pointwise on $\Delta(a,r)\subset D$ for some $r>0$, thus it converges normally to a holomorphic function $p\in H(\Delta(a,r))$ by [[Series of Complex Functions#^615906|Abel's theorem]]. Now we define $g\colon D\cup\{a\} \to \C$ by$$g(z)=\begin{cases}\frac{f(z)}{(z-a)^{N}}&z\neq a\\p(a)&z=a\end{cases}$$Then $g$ is [[Complex Differentiability#^44f14c|complex differentiable]] on $D\setminus\{a\}$ since it equals to $\frac{f(z)}{(z-a)^{N}}$. And is complex differentiable on $a$ since it agrees with $p$ on $\Delta(a,r)$. Therefore $g\in H(D\cup\{a\})$, as required.
Now consider uniqueness. Suppose $f(z)=(z-a)^{N_{1}}g_{1}(z)=(z-a)^{N_{2}}g_{2}(z)$ with $N_{1}\neq N_{2}$ and $g_{1}(a)\neq 0$, $g_{2}(a)\neq 0$. Without loss of generality, assume $N_{1}>N_{2}$. Then $$(z-a)^{N_{1}-N_{2}}g_{1}(z)=g_{2}(z)\quad \text{for all } z\in D\setminus\{a\} $$Since $g_{1}, g_{2}$ are holomorphic, thus continuity at $a$ implies that $$0=\lim_{z\to a}(z-a)^{N_{1}-N_{2}}g_{1}(z)=g_{2}(a) $$yielding a contradiction. Therefore $N_{1}=N_{2}$, and $g_{1}(z)=g_{2}(z)$ for all $z\neq a$. Thus $g_{1}=g_{2}$ on $D\cup\{a\}$ by continuity. $\square$

> [!theorem] Characterization of Poles
> Let $f\in H(D)$, and $a\in \C$ is an isolated singularity of $f$. Then $a$ is a pole iff $\lim_{z\to a}|f(z)|=\infty$.

*Proof*  Suppose $f$ has a pole at $a$. Write $f(z)=(z-a)^{-N}g(z)$ for some $N\in\N$ and $g\in H(D\cup\{a\})$ with $g(a)\neq 0$. Then $$\lim_{z\to a}|f(z)|=\lim_{z\to a}|z-a|^{-N}|g(z)|=\infty$$Conversely, suppose $\lim_{z\to a}|f(z)|=\infty$. Then $|f(z)|>47$ on some $\Delta(a,0,\epsilon)\subset D$. That is $\frac{1}{|f(z)|}\leq \frac{1}{47}$. Therefore $\frac{1}{f}$ is bounded on $\Delta(a,0,\epsilon)$, so $\frac{1}{f}$ has a removable singularity at $a$. Let $g$ be the holomorphic extension of $\frac{1}{f}$ to $D\cup\{a\}$. Then $$|g(a)|=\lim_{z\to a}|g(z)|=\lim_{z\to a} \frac{1}{|f(z)|}=0$$Hence $g(a)=0$. Since $g\neq 0$, by [[Isolated Singularities#^183f67|the lemma]], we can write $g(z)=(z-a)^{M}p(z)$ where $p\in H(\Delta(a,r))$ with $p(a)\neq 0$. Then for $z\neq a$, we have $$f(z)=\frac{1}{g(z)}=\frac{1}{(z-a)^{M}p(z)}=(z-a)^{-M}\frac{1}{p(z)}$$As $p(a)\neq 0$, $\frac{1}{p}$ is holomorphic on some $\Delta(a,r')$, by Taylor expansion, we have $\frac{1}{p(z)}=\sum_{n=0}^{\infty}c_{n}(z-a)^{n}$, so $$f(z)=(z-a)^{-M}\sum_{n=0}^{\infty}c_{n}(z-a)^{n}=\sum_{n=-M}^{\infty}c_{n+M}(z-a)^{n}$$This shows that $a$ is a pole of $f$ by definition. $\square$

>[!remark]+
>Another way to think about poles is that $f$ extends to a holomorphic function from $D∪\{a\}$ into the Riemann sphere $\hat{\C}$.

> [!definition] Order of Pole and Zero
> If $f\in H(D)$ has a pole at $a$, then we can write $f(z)=(z-a)^{-N}g(z)$ for some $N\in\N$ and $g\in H(D\cup\{a\})$ with $g(a)\neq 0$. Such $N$ is called the order of the pole at $a$. Similarly, if $f\in H(D)$ and $a\in D$ with $f(a)=0$, then $N$ is called the order of the zero at $a$ if $f(z)=(z-a)^{N}g(z)$ for some $N\in\N$ and $g\in H(D)$ with $g(a)\neq 0$. We call zero of order $1$ a simple zero, pole of order $1$ a simple pole.

The order of a zero is telling you how quickly $f(z)$ approaches $0$ as $z → a$, and similarly the order of a pole tells you how quickly $f(z)$ approaches $∞$ as $z →a$.

>[!corollary]
>If $f$ has a pole/zero of order $N$ at $a$, then $1/f$ has a zero/pole of order $N$.

> [!corollary]
> 1. If $f$ has a zero of order $N$ at $a$ and $g$ has a zero of order $M$ at $a$, then $f(z)g(z)$ has a zero of order $N + M$ at $a$.
> 2. Similarly, if $f$ has a pole of order $N$ at $a$ and $g$ has a pole of order $M$ at $a$, then $f(z)g(z)$ has a pole of order $N + M$ at $a$.
> 3. If $f$ has a zero of order $N$ at $a$ and $g$ has a pole of order $M$ at $a$, then
> 	- If $M >N$, then $f(z)g(z)$ has a pole of order $M−N$ at $a$.
> 	- If $N ≥M$, then $f(z)g(z)$ has a removable singularity at $a$, and if $N >M$ then (once we remove the singularity) it becomes a zero of order $N−M$.
> $\quad$

> [!definition] Meromorphic Function
> A function $f$ is called *meromorphic* on $D$ if $f$ is holomorphic on $D$ except for some isolated singularities which are poles.

## Characterise Essential Singularities

> [!theorem] Casorati-Weierstrass Theorem
> Let $f\in H(D)$, and $a$ is an essential singularity of $f$. Then for any $A\in\C\cup\{\infty\}$, there is a sequence $(z_{n})\subset D$ with $z_{n}\to a$ and $f(z_{n})\to A$.

*Proof*  Case $A=\infty$. Since the singularity is not removable, $f$ is unbounded on every $\Delta(a,0,\varepsilon)$, so we may choose $z_{n}\in \Delta(a,0,\frac{1}{n})$ such that $|f(z_{n})|\geq n$. Then $z_{n}\to a$ and $f(z_{n})\to \infty$.
Next consider $A\in\C$ and there exists a sequence $(z_{n})\subset D$ with $z_{n}\to a$ and $f(z_{n})= A$ for all $n$. The result is immediate.
Now if $A\in\C$ and there is no such sequence, then there exists $\varepsilon>0$, such that $f(z) \neq A$ for all $z ∈∆(a,0,\varepsilon)$. Consider $g(z)=\frac{1}{f(z)-A}$. $f(z)-A$ has an essential singularity at $A$, because adding $-A$ only affects the constant term of the Laurent series. Notice that $g\in H(a,0,\varepsilon)$ has an isolated singularity at $a$. If it had a pole or removable singularity, then its reciprocal, $f(z)-A$, would have a pole or removable singularity at $a$, yielding a contradiction. Therefore $g$ has an essential singularity at $a$. Now apply case 1 to $g$ to get a sequence $(z_{n})\subset D$ with $z_{n}\to a$ and $g(z_{n})\to\infty$. This implies that $f(z_{n})\to A$. $\square$

> [!theorem] Great Picard Theorem
> If $f$ has an essential singularity at $a$, then for any $\varepsilon$ the set $f(∆(a,0,\varepsilon))$ is either $\C$ or $\C \setminus\{b\}$ for some $b ∈\C$.
