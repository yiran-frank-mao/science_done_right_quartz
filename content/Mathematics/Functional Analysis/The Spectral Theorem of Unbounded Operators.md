> [!proposition]
> Let $(X, \mu)$ be a measure space with $\mu$ a finite measure. Suppose that $f$ is a measurable, real-valued function on $X$ which is finite a.e. Then the operator $T_{f}\colon \varphi \mapsto f \varphi$ on $L^2(X,\mu)$ with domain
> $$ D(T_f) = \{\varphi\mid  f\varphi \in L^2(X, \mu)\} $$
> is self-adjoint and $\sigma(T_f)$ is the essential range of $f$.

> [!theorem] Spectral Theorem - Multiplication Operator Form
> Let $T$ be a self-adjoint operator on a separable Hilbert space $\H$. Then there exists a [[Measurable Spaces and Functions#^c2e020|measure space]] $(X,\mu)$ with $\mu$ finite, a unitary operator $U\colon \H\to L^{2}(X,\mu)$, and a real-valued function $f$ on $X$ which is finite a.e. such that
> - $\psi\in D(T)$ if and only if $x\mapsto f(x)(U\psi)(x)\in L^{2}(X,\mu)$;
> - If $\varphi\in U(D(T))$, then $(UTU^{-1}\varphi)(x)=f(x)\varphi(x)$.
>$\quad$ ^d20d30

## The Functional Calculus Form

> [!theorem] Spectral Theorem - Functional Calculus Form
> Let $T$ be a self-adjoint operator on a separable Hilbert space $\H$. Then there exists a unique map $\Phi\colon B_{b}(\R)\to B(\H)$ such that 
> - $\Phi$ is a [$\ast$-homomorphism](C*-Algebras.md#^1a6445);
> - $\Phi$ is norm continuous. i.e., $\|\Phi(h)\|_{B(\H)}\leq \|h\|_{\infty}$;
> - If $\{h_{n}\}_{n=0}^{\infty}\subset B_{b}(\R)$ is a sequence of bounded Borel functions with $h_{n}(x)\to x$ for each $x$ and $|h_n(x)| \leq |x|$ for all $x$ and $n$. Then, for any $\psi \in D(T)$, $\lim_{n\to\infty} \Phi(h_{n})\psi = T\psi$.
> - If $h_n(x) \to h(x)$ pointwise and if the sequence $\|h_n\|_{\infty}$ is bounded, then $\Phi(h_n) \to \Phi(h)$ strongly.
> $\quad$ ^bb27f4

<u><b>e.g.</b></u>  If $A$ is an unbounded positive self-adjoint operator on $\H$. Then 

## The Projection Valued Measure Form

> [!definition] Projection Valued Measure
> 



> [!theorem] Spectral Theorem - Projection Valued Measure Form
> There exists a one-to-one correspondence between self-adjoint operators on a separable Hilbert space $\H$ and projection valued measures $\{P_{\Omega}\}$ on $\H$: $$T=\int_{\R} \lambda\dd P_{\lambda}$$
> 

