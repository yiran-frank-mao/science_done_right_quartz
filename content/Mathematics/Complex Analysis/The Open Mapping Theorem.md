---
created: 2024-10-16
updated: 2024-10-19
completed: true
---
> [!lemma]
> Suppose $\newcommand{\R}{\mathbb{R}}\newcommand{\C}{\mathbb{C}}f\colon D \to \C$. Then $w ∈f(D)$ if and only if $K_{f−w,D}≥1$, where $f−w$ is short for the function $z\mapsto f(z)−w$. ^1d5387

*Proof*  By definition, $K_{f−w,D}≥1$ means that the $f-w$ has at least one zero on the domain $D$. That is $f(z_0)-w=0$ for some $z_0\in D$, thus $w\in f(D)$. The converse is also true by the same arguments. $\square$

> [!theorem] Open Mapping Theorem
> Let $D$ be a domain and let $f ∈H(D)$ be a non-constant function. Then $f(D)$ is open. ^6df1f8

*Proof*  Fix some $f(z_{0})=w_0 \in f(D)$, we must show that some open disk around $w_0$ is contained in $f(D)$. Since $f$ is non-constant, we can pick some $r>0$ such that $f(z)\neq w_0$ for all $z\in\overline{\Delta(z_0 ,r )} \setminus \{z_0\}$. If such $r$ doesn't exist, then there would exist a sequence $(z_n)$ such that $f(z_n )=w_0$ for all $n$, then by the uniqueness theorem, $f$ would be constant, which yields a contradiction. Now let $$\rho=\min_{|z-z_{0}|=r}|f(z)-w_{0}|$$We have $\rho>0$ since $f(z)\neq w_0$ on $\partial \Delta(z_0, r)$.  Notice that the minimum can be achieved as the boundary is compact and $|f(z)-w_0|$ is continuous.
We will now show that $\Delta(w_{0}, \rho)\subset f(D)$. Let $w\in \Delta(w_{0},\rho)$, consider$$f(z)-w=(f(z)-w_{0})+(w_{0}-w)$$For $z\in \partial\Delta(z_{0},r)$, we have $$|w_{0}-w|<\rho\leq|f(z)-w_{0}|$$Hence we can apply the [[The Argument Principle#^fc2a0d|Rouché's  theorem]] to $f-w$ to obtain$$K_{f-w,\Delta(z_{0},r)}=K_{f-w_{0},\Delta(z_{0},r)}\geq1$$By [[The Open Mapping Theorem#^1d5387|lemma]], this implies that $w\in f(D)$, therefore $\Delta(w_{0}, \rho)\subset f(D)$, and so $f(D)$ is open. $\square$

> [!theorem]
> Let $f ∈H(D)$ and suppose $f'(z_{0}) = 0$ for some $z_{0} ∈D$. Then $f$ is not injective.

*Proof*  Since $f'(z_{0})=0$, we fix such $z_{0}\in D$ similar to the above arguments, we can still obtain $$K_{f-w,\Delta(z_{0},r)}=K_{f-w_{0},\Delta(z_{0},r)}$$But since $f'(z_{0})=0$, $K_{f-w_{0},\Delta(z_{0},r)}\geq 2$. So there are two cases:
1. there exist $z_{1},z_{2}\in \Delta(z_{0},r)$ such that $z_{1}\neq z_{2}$ but $f(z_{1})=f(z_{2})\in \Delta(w_{0},\rho)$;
2. if $z\in \Delta(z_{0},r)$ and $f(z)\in \Delta(w_{0},\rho)$, then $f'(z)=0$.

In fact, the second option would imply that $f'$ is zero on $\Delta(z_{0}, r)\cap f^{-1}(\Delta(w_{0},\rho))$, and so $f'$ is identically zero on $D$ by [[Series Expansion of Holomorphic Functions#^b5768d|uniqueness theorem]]. That is saying that $f$ is constant, yielding a contradiction. Thus only the first option holds, which implies $f$ is not injective. $\square$

>[!corollary]
>If $f\in H(D)$ is injective, than $f'(z)\neq 0$ for all $z\in D$. ^bf7ce8

*Proof*  Simply contrapositive of the above theorem, yet might be more useful. $\square$

>[!remark]+ The above isn't true in $\R^n$
>Attention that the above is not generally true in real analysi. Consider real function $f(x)=x^3$, it satisfies $f'(0)=0$ but $f$ is injective.

> [!theorem]
> Let $f ∈H(D)$ be injective. Then $G= f(D)$ is a domain and $f \colon D→G$ is biholomorphic. ^2ea31f

*Proof*  By the [[The Open Mapping Theorem#^6df1f8|open mapping theorem]], $G$ is open. $G$ is connected since $f$ is continuous. So $G$ is a domain. By the above corollary, as $f$ is injective, $f'(z)\neq 0$ for all $z\in D$. Hence the Jacobian of $f$ is non-zero: $$J_{f}(z)=\begin{pmatrix}a & -b \\ b & a\end{pmatrix}$$with $a,b$ not both zeroes. And thus $\det(J_{f}(z))=a^2+b^2>0$, which indicates that the Jacobian is invertible at every $z\in D$. Thus by the [inverse function theorem](https://en.m.wikipedia.org/wiki/Inverse_function_theorem), we know that $f^{-1}$ is $\R$-differentiable, and $$J_{f^{-1}}(f(z))=J^{-1}_{f}(z)=\frac{1}{a^2 +b ^2}\begin{pmatrix}a & b \\ -b & a\end{pmatrix}$$Thus $f^{-1}$ also satisfies the [[Complex Differentiability#^cf170c|Cauchy-Riemann equations]], therefore [[Holomorphic and Conformal Maps#^c7e434|holomorphic]]. $\square$

## Maximum Modulus Principle

>[!theorem] Strong Maximum Modulus Principle
> Let $D$ be a domain and $f\in H(D)$. If $|f|$ attains its maximum at some $z_0\in D$, then $f$ is constant. ^5a8a82

*Proof*  Suppose $|f(z_0)|\geq |f(z)|$ for all $z\in D$, but $f$ is not constant. Then by [[The Open Mapping Theorem#^6df1f8|open mapping theorem]], $f(D)$ is open. Thus there exists some $r>0$ such that $\Delta(f(z_0),r)\subset f(D)$. So $\left(1+\frac{r}{2|f(z_{0})|}\right)f(z_{0})\in\Delta(f(z_{0},r))$ has a greater modulus than $f(z_{0})$, yielding a contradiction. $\square$

> [!theorem] Weak Maximum Modulus Principle
> If $D$ is a bounded domain and $f\in H(D)\cap C(\overline{D})$, then $|f|$ attains its maximum on $\partial D$. i.e. $$\max_{z\in\overline{D}}|f(z)|=\max_{z\in\partial D}|f(z)|$$ ^34ad01

*Proof*  If $f$ is constant, then the result is trivial. Otherwise, by the [[The Open Mapping Theorem#^6df1f8|open mapping theorem]], $f(D)$ is open. Similar to the weak maximum principle, we can show that the maximum cannot be achieved in the [[Interior, Exterior and Boundary#^7741a2|interior]] of $D$. $\square$







