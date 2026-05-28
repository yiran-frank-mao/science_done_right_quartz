---
created: 2025-08-28
updated: 2025-09-05
tags:
  - functional-analysis
  - operator-theory
  - quantum-mechanics
completed: true
---
This note explore Nelson’s commutator theorem, which delivers sufficient conditions for a symmetric operator to be essentially self-adjoint.

## Scales of Hilbert Spaces

> [!definition] Scales of Hilbert Spaces
> Let $H$ be a positive [[Symmetric and Self-Adjoint Operators#^450e4c|self-adjoint]] operator on a [[Hilbert Spaces#^ae0212|Hilbert space]] $\newcommand{\H}{\mathcal{H}}\newcommand{\L}{\mathscr{L}}\newcommand{\R}{\mathbb{R}}(\H,\langle\cdot,\cdot\rangle)$. For any $k \in \mathbb{R}$, we define the Hilbert space $(\H^{k},\langle\cdot,\cdot\rangle_{k})$ as the completion of the domain $D(H^{k/2})$ ($H^{k/2}$ is the operator obtained from [[The Spectral Theorem of Unbounded Operators#^bb27f4|functional calculus]]) with respect to the inner product:
> $$\langle f, g \rangle_k := \langle (I+H)^{k/2}f, (I+H)^{k/2}g \rangle.$$
> These are called *scales* of $\H$ associated with $H$. We also define
> $$\H^{\infty} := \bigcap_{k \in \R} \H^{k},\quad\H^{-\infty} := \bigcup_{k \in \R} \H^{k}.$$
> Moreover, for $g\in\H^{-k}$ and $f\in \H^{k}$, we define $$\langle g,f\rangle_{-k,k}:=\left\langle (I+H)^{-k/2} g, (I+H)^{k/2} f \right\rangle.$$ ^eec324

> [!remark]+
> Scales generalize Sobolev spaces. The powers $H^{k/2}$ define norms that distinguish different levels of regularity. Intuitively, higher $k$ corresponds to more “smooth” or “regular” elements (stronger norms), while lower (even negative) $k$ relate to dual or distribution-type spaces. Specifically, $\langle\cdot,\cdot\rangle_{-k,k}$ provides a duality between $\H^{k}$ and $\H^{-k}$.

<u><b>e.g.</b></u>  


Throughout this note, we will assume that $H$ is a [[Symmetric and Self-Adjoint Operators#^450e4c|self-adjoint]] positive operator on $\H$. The following properties are immediate from the definition:

> [!proposition]
> The following properties hold:
> 1.  For $k_1 > k_2$, we have a continuous inclusion $\H^{k_1} \subset \H^{k_2}$.
> 2.  The operator $(1+H)^t$ is a unitary map from $\H^k \to \H^{k-2t}$.
> 3. $\| w \|_{1}\geq \|w\| \geq \| w \|_{-1}$.
> $\quad$ ^af59cb

*Proof*  (1) and (2) are immediate from our construction. For (3), note that $$\| w \|_{1}^{2} = \langle (I+H)^{1/2} w, (I+H)^{1/2} w \rangle =\langle (I+H) w,  w \rangle = \|w\|^{2} + \|H^{1/2}\|^{2}, $$so $\| w \|_{1}\geq \|w\|$. Moreover, by [[The Spectral Theorem of Unbounded Operators#^bb27f4|the spectral theorem]], since the function $\lambda\mapsto(1+\lambda)^{−1/2}$ is continuous and bounded on $[0,\infty)$, with maximum value $1$ at $λ=0$, $(I+H)^{-1/2}$ is a bounded operator with operator norm less than or equal to $1$. Thus, $$\| w \|_{-1} = \| (I+H)^{1/2}w \| \leq \|w\|. $$ $\square$

> [!proposition]
> $\H^{\infty}$ is [[Closure, Interior and Boundary#^b560bf|dense]] in $\H^k$ for all $k\in\R$. In particular, $\H^{\infty}$ is dense in $\H$.

*Proof*  By the [[The Spectral Theorem of Unbounded Operators#^d20d30|spectral theorem]], we can think of vectors in $\H$ as a function $\psi$ and the operator $H$ as multiplication by an a.e. finite function $h$. Formally, there exists a measure space $(X,\mu)$ so that $\psi\in\H^{k}$ if and only if $\newcommand{\dd}{\,\mathrm{d}}\int (1+h(x))^{k}|\psi(x)|^{2} \dd\mu$ is finite.
Now suppose $\psi\in\H^{k}$. We can construct a sequence of approximating vectors, $$\psi_{n}(x):=\begin{cases}\psi(x), \quad& \text{if } h(x)\leq n, \\ 0 ,\quad &\text{otherwise}.\end{cases}$$Then $\int (1+h(x))^{l}|\psi_{n}(x)|^{2} \dd\mu$ is finite for all $l\in\R$. So $\psi_{n}\in\H^{l}$ for all $l\in\R$, which means $\psi_{n}\in \H^{\infty}$ for all $n\in\mathbb{N}$. Note that $$\|\psi-\psi_n\|_k^2=\int_{h(\lambda)>n}(1+h(x))^k|\psi(x)|^2\dd\mu<\infty, $$because we started with the assumption that $\psi\in\H^{k}$, we know the total integral is finite. Then this integral approaches to zero as $n\to \infty$. We've just found an element in $\H^{\infty}$ that can be arbitrarily close to $\psi$, this means $\H^{\infty}$ is dense in $\H^{k}$. $\square$

> [!definition] Operator Spaces
> For $-\infty \le k, l \le \infty$, we define two spaces of linear operators:
> - $\L(\H^k, \H^l)$ is the space of bounded linear operators from $\H^k$ to $\H^l$, equipped with the [[Orthogonality and Bounded Linear Maps#^f95b62|operator norm]] denoted by $||\cdot||_{k,l}$.
> - $\L_0(\H^k, \H^l)$ is the space of linear operators with domain $\H^\infty$ which can be extended by continuity to an operator in $\L(\H^k, \H^l)$.
> 
> As usual, if $k=l$, we simplify our notation to $\L(\H^{k})$ and $\L_{0}(\H^{k})$ respectively.

> [!remark]+
> $\L_{0}(\H^{k},\H^{l})$ and $\L(\H^{k},\H^{l})$ are in fact isomorphic. Any $T\in \L(\H^k, \H^l)$ can be restricted to $\H^{\infty}$.

## Commutator Properties

We define the adjoint action of $H$ on an operator $A$ $\newcommand{\ad}{\mathrm{ad}}(\ad H)A := [H,A] = HA - AH$ as usual.

> [!lemma]
> If $A \in \L_0(\H^k, \H^l)$, then its commutator with $H$, $(\ad H)A$, belongs to $\L_0(\H^{k+2}, \H^{l-2})$.

*Proof*  Let $f \in \H^{k+2}$. Then $Hf \in\H^{k}$, $AH f \in \H^{l}$, $Af \in \H^{l}$ and $HAf \in \H^{l-2}$. So $(\ad H)Af = HAf - AHf \in \H^{l-2}$. Moreover, we have the bound: $$\begin{aligned} \|(\ad H)A\|_{k+2,l-2} &= \|HA - AH\|_{k+2,l-2} \\ &\leq \|H A\|_{k+2,l-2} + \|A H\|_{k+2,l-2} \\ &= \|A\|_{k,l} + \|A\|_{k,l} \\ &<\infty.\end{aligned}$$Thus, $(\ad H)A \in \L_0(\H^{k+2}, \H^{l-2})$. $\square$

> [!lemma] Regularity Lemma
> If $(\ad H)^m A \in \L_0(\H^k, \H^l)$ for $m = 0, 1, \dots, n$, then $A \in \L_0(\H^{k+2n}, \H^{l+2n})$. 
> Consequently, if this holds for all $m \ge 0$, then $A$ is smooth, i.e., $A \in \L(\H^\infty)$. ^de9d4d

*Proof*  It suffices to prove the case for $n=1$ as the general statement follows by induction. Assume $A, [H,A] \in \L_0(\H^k, \H^l)$. We want to show $A \in \L_0(\H^{k+2}, \H^{l+2})$. Firstly, $HA=[H,A]+AH$, so it maps any $f\in\H^{k+2}$ to $\H^{l}$, thus $A$ maps $\H^{k+2}$ to $\H^{l+2}$. 
Secondly, we need to show that $\|A\|_{k+2,l+2}<\infty$. Since $I+H\colon \H^{k+2} \to \H^{k}$ is unitary, we have $\| A(I+H) \|_{k+2,l}=\|A\|_{k,l}$. Note that $$\|(I+H)A-A(I+H)\|_{k+2,l}=\|[H,A]\|_{k+2,l}\leq\|[H,A]\|_{k,l}.$$Therefore by triangle inequality, $$\begin{aligned}\|(I+H)A\|_{k+2,l}&\leq\|(I+H)A-A(I+H)\|_{k+2,l}+\|A(I+H)\|_{k+2,l}\\&\leq\|[H,A]\|_{k,l} + \|A\|_{k,l} < \infty.\end{aligned}$$$\square$

## Nelson's Commutator Theorem

> [!definition] Formal Adjoint
> If $A \in \L_0(\H^k, \H^l)$, we define its *formal adjoint* $A^\dagger \in \L_0(\H^{-l}, \H^{-k})$ as the operator satisfying:
> $$\langle A^\dagger v, w \rangle_{-k,k} = \langle v, Aw \rangle_{-l,l} \quad \forall w, v \in \H^\infty.$$
> We say that $A$ is *formally Hermitian* if $A = A^\dagger$. ^c1eb50

Suppose $T^*$ is the adjoint of $T$ with respect to $\langle\cdot,\cdot\rangle_{k}$ and $\langle\cdot,\cdot\rangle_{l}$. That is, 
    \[ \langle Tv, w \rangle_{l} = \langle v, T^*w\rangle_{k} \]
    for all $v\in \H^k$ and $w\in \H^l$. We can give an expression for \(T^{\dagger}\) in terms of $T^*$ by observing the following: 
    \[\begin{aligned}
        \langle v,Tw\rangle_{-l,l} &= \left\langle (\id+A)^{-l/2}v, (\id+A)^{l/2}T w\right\rangle \\ 
        &= \left\langle (\id+A)^{-l}v, Tw \right\rangle_l \\ 
        &= \left\langle T^{*}(\id+A)^{-l}v, w\right\rangle_{k} \\ 
        &= \left\langle (\id+A)^{k/2}T^{*}(\id+A)^{-l}v, (\id+A)^{k/2}w\right\rangle \\ 
        &= \left\langle (\id+A)^{k}T^{*}(\id+A)^{-l}v, w\right\rangle_{-k,k}.\end{aligned}\]
    Therefore \(T^{\dagger}=(\id+A)^{k} T^{*}(\id+A)^{-l}\).

We can give an expression for $A^{\dagger}$ by observing the following: $$\begin{aligned}\langle v,Aw\rangle_{-l,l} &= \left\langle (I+H)^{-l/2}v, (I+H)^{l/2}A w\right\rangle \\ &= \left\langle (I+H)^{-l/2}v, (I+H)^{l/2}A(I+H)^{-k} (I+H)^{k}w \right\rangle \\ &= \left\langle (I+H)^{k}A(I+H)^{-l/2} (I+H)^{-l/2}v, (I+H)^{k}w\right\rangle_{-k} \\ &= \left\langle (I+H)^{k}A^{*}(I+H)^{-l}v, (I+H)^{k}w\right\rangle_{-k} \\ &= \left\langle (I+H)^{-k/2}(I+H)^{k}A^{*}(I+H)^{-l}v, (I+H)^{-k/2}(I+H)^{k}w\right\rangle \\ &= \left\langle (I+H)^{k}A^{*}(I+H)^{-l}v, w\right\rangle_{-k,k}.\end{aligned}$$Therefore $A^{\dagger}=(I+H)^{k} A^{*}(I+H)^{-l}$.

> [!lemma]
> Let $H$ be a positive self-adjoint operator on a Hilbert space $\mathcal{H}$, and let $A$ and $[H,A]$ be in $\L_{0}(\H^{1},\H^{-1})$. For any $\varepsilon > 0$, the following identity holds:
> $$ [A, e^{-\varepsilon H}] = -\int_{0}^{\varepsilon} e^{-(\varepsilon-s)H} [A,H] e^{-sH} \dd s.$$ ^da0180

*Proof*  Define a one-parameter family of operators $F(s)$ for $s \in [0, \varepsilon]$: $$ F(s) = e^{-(\varepsilon-s)H} A e^{-sH}. $$We differentiate $F(s)$ with respect to $s$ using the product rule: $$ F'(s) =  F'(s) = H e^{-(\varepsilon-s)H} A e^{-sH} - e^{-(\varepsilon-s)H} A H e^{-sH}  $$By the [[The Spectral Theorem of Unbounded Operators#^bb27f4|functional calculus]] for the self-adjoint operator $H$, $H$ commutes with $e^{-(\varepsilon-s)H}$, so we can factor it out: $$ F'(s) = e^{-(\varepsilon-s)H} (HA - AH) e^{-sH} = -e^{-(\varepsilon-s)H} [A,H] e^{-sH} $$By the fundamental theorem of calculus for operator-valued functions, we integrate $F'(s)$ from $0$ to $\varepsilon$: $$ F(\varepsilon) - F(0) = \int_{0}^{\varepsilon} F'(s) \dd s, $$it follows that $$ A e^{-\varepsilon H} - e^{-\varepsilon H} A = -\int_{0}^{\varepsilon} e^{-(\varepsilon-s)H} [A,H] e^{-sH} \dd s. $$This is precisely the desired identity for $[A, e^{-\varepsilon H}]$. $\square$

> [!theorem] Nelson's Commutator Theorem
> Let $H$ be a positive self-adjoint operator on a Hilbert space $\mathcal{H}$, and let $A$ and $[H,A]$ be in $\L_{0}(\H^{1},\H^{-1})$. Then the closure of its formal adjoint $\overline{A^\dagger}$ equals $A^*$. In particular, if $A$ is formally Hermitian, it is essentially self-adjoint. ^edbb20

 > [!remark]+
> If $A$ and $[H,A]$ are in $\L_{0}(\H^{1},\H^{-1})$, then so are $A^{\dagger}$ and $[H,A^{\dagger}]$. By [[Nelson's Commutator Theorem#^de9d4d|the lemma]], $A$ and $A^{\dagger}$ are in $\L_{0}(\H^{3},\H^{1})$. Note that $\H^{1}\subset \H$, so $A$ and $A^{\dagger}$ are densely defined operators on $\H$, and $A^{*}$ is well-defined.

*Proof*  It is clear that $A^{\dagger}\subset A^{*}$, because for all $w,v\in\H^{\infty}$, since $I+H$ is self-adjoint in $\H$, we have $$ \langle A w,v\rangle = \left\langle (I+H)^{-1/2} Aw, (I+H)^{1/2}v\right\rangle = \langle Aw,v\rangle_{-1,1}=\langle w, A^{\dagger} v\rangle_{1,-1}=\langle w, A^{\dagger} v\rangle. $$It remains to show that the graph of $A^{*}$ is contained in the graph of $\overline{A^{\dagger}}$, denoted $\Gamma(\overline{A^\dagger})$.
Pick some $0<\varepsilon\leq 1/2$. By [[Nelson's Commutator Theorem#^da0180|the above lemma]], we have the identity $$[A, e^{-\varepsilon H}] = -\int_{0}^{\varepsilon} e^{-(\varepsilon-s)H} [A,H] e^{-sH} \dd s.$$Taking the operator norm on both sides: $$ \left\|[A, e^{-\varepsilon H}]\right\| \leq \int_{0}^{\varepsilon} \|e^{-(\varepsilon-s)H}\|_{-1,0} \cdot \|[A,H]\|_{1,-1} \cdot \|e^{-sH}\|_{0,1} \dd s.$$Note that the norm continuity property of [[The Spectral Theorem of Unbounded Operators#^bb27f4|functional calculus]] gives $$ \|e^{-sH}\|_{0,1} = \|(1+H)^{1/2} e^{-sH}\| \leq \sup_{\lambda \in [0, \infty)} (1+\lambda)^{1/2} e^{-s\lambda} = (2s)^{-1/2} e^{-1/2+s}. $$A similar calculation yields $\|e^{-(\varepsilon-s)H}\|_{-1,0} \leq (2(\varepsilon-s))^{-1/2}e^{-1/2+\varepsilon-s}$. Therefore, plugging these bounds into the integral, we obtain $$ \begin{aligned} \|[A, e^{-\varepsilon H}]\| &\leq \|[A,H]\|_{1,-1} \int_{0}^{\varepsilon} (4s(z\varepsilon-s))^{-\frac{1}{2}}e^{-1+\varepsilon} \dd s \\ &= \frac{\|[A,H]\|_{1,-1}}{2e^{1-\varepsilon}} \int_{0}^{\varepsilon} \frac{1}{\sqrt{s(\varepsilon-s)}} \dd s \\ &= \frac{\pi}{2} e^{\varepsilon-1} \|[A,H]\|_{1,-1}. \end{aligned} $$So $[A, e^{-\varepsilon H}]$ is a bounded operator on $\mathcal{H}$ for any $1/2\geq \varepsilon > 0$. Let $R_\varepsilon = \overline{[A, e^{-\varepsilon H}]}\in \L(\H)$. For any $f \in \H^{\infty}$, $$R_{\varepsilon} f = [A, e^{-\varepsilon H}]f \to  0, \quad  \text{as } \varepsilon\to 0.$$Since $\H^{\infty}$ is [[Closure, Interior and Boundary#^b560bf|dense]] in $\H$, and $\|R_{\varepsilon} \| <\infty$ as $\varepsilon \to 0$, we conclude that $R_{\varepsilon} \to \hat{0}$ in the strong operator topology.
Now consider a vector $w \in D(A^*)$, we want to show that $(w, A^*w)$ is in $\Gamma(\overline{A^\dagger})$. For any $f\in\H^{\infty}$, we have $$ \langle A^{\dagger} e^{-\varepsilon H} w+ R_{\varepsilon}^{*}w-e^{-\varepsilon H}A^{*}w,f\rangle=\langle w,e^{-\varepsilon H}Af+R_\varepsilon f-Ae^{-\varepsilon H}f\rangle=0.$$So $(A^{\dagger}e^{-\varepsilon H}+R_{\varepsilon}^{*})_{w}=(e^{-\varepsilon H}A^{*})w$. As the adjoints of strongly continuous operators are weakly convergent, $(w,A^{*}w)$ is in the weak closure of $\Gamma(A^{\dagger})$. Note that the graph of any linear operator is convex, so weak convergence implies strong convergence. Therefore, $(w,A^{*}w)$ is in the strong closure of $\Gamma(A^{\dagger})$, which is $\Gamma(\overline{A^{\dagger}})$. $\square$

## References
[Nelson (1972), Time-ordered operator products of sharp-time quadratic forms](https://doi.org/10.1016/0022-1236(72)90091-2)