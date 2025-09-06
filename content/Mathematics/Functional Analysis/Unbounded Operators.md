The position operator in quantum mechanics is unbounded. Specifically, consider $\newcommand{\H}{\mathcal{H}}\H=L^2(\R)$ and let $D(T)$ be the set of all functions $f\in L^2(\R)$ such that $\int_{\R} x^{2}|f(x)|^{2}\dd x<\infty$. For $f\in D(T)$, the position operator $T$ acts on $f$ such that $$(Tf)(x)=xf(x).$$Then $T$ is clearly unbounded because we can consider $f_{n}\in L^{2}(\R)$ satisfying $$f_{n}(x):=\begin{cases}1, \quad \text{if }x\in[n,n+1], \\ 0,\quad \text{otherwise}.\end{cases}$$Then $\|f_{n}\|=1$, but $\|T f_{n}\|=\int_{\R} x^{2}|f_{n}(x)|^{2}\dd x=\frac{1}{3}((n+1)^{3}-n^{3})$, which diverges to $\infty$ as $n\to\infty$.

> [!definition] Domain of an Operator
> 
> 


> [!definition] Closed Operator
> An operator $T\colon \H_{1}\to \H_{2}$ between two Hilbert spaces is called closed if for any sequence $\{f_{n}\}\subset D(T)$, $f_{n}\to f$ and $T f_{n}\to g$ implies $f\in D(T)$ and $T f=g$. Equivalently, $T$ is closed if its [[Relations and Functions#^bd51b5|graph]] is closed in $\H_{1}\times \H_{2}$.
> 

<u><b>e.g.</b></u>  Clearly, any bounded linear operator is closed.

> [!definition] Extension
> Let $T_{1},T_{2}\colon \H_{1}\to \H_{2}$ be operators between two Hilbert spaces. We say that $T_{1}$ is an extension of $T_{2}$ if their graphs satisfy $\Gamma(T_{1})\supset \Gamma(T_{2})$ and we write $T_{1}\supset T_{2}$.

> [!proposition]
> $T_{1}\supset T_{2}$ if and only if $D(T_{1})\supset D(T_{2})$ and $T_{1}f=T_{2}f$ for all $f\in D(T_{2})$.
> 

*Proof*  

> [!definition] Closable
> An operator is closable 

<u><b>e.g.</b></u>  Let $\H=L^{2}(\R)$, two operators $T_{1}:=i \ddf{}{x}$ and $T_{2}:=i\ddf{}{x}$ but defined on two different domains: $D(T_{1})=C^{1}_{0}(\R)$, $D(T_{2})=C^{\infty}_{0}(\R)$. Then $T_{2}\subset T_{1}$. 

## Adjoints of Densely Defined Operators

> [!definition] Adjoint of Densely Defined Operator
> Let $T\colon \H_{1}\to \H_{2}$ be a densely defined (i.e. $D(T)$ is [[Closure, Interior and Boundary#^b560bf|dense]] in $\H_{1}$) operator between Hilbert spaces. Define the adjoint operator $T^{*}\colon \H_{2}\to \H_{1}$ on the domain $$D(T^*):=\left\{f\in \H_{2} \mid \exists g\in\H_{2}. \langle T\varphi,f\rangle =\langle \varphi,g\rangle \text{ for all } \varphi\in D(T) \right\}$$ such that $$\langle Tf,g\rangle=\langle f,T^{*}g\rangle$$ for all $f\in D(T)$ and $g\in D(T^{*})$. ^db609c

The following proposition guarantees the unique existence of adjoints for unbounded operators under certain conditions:

> [!proposition]
> The adjoint of a densely defined operator is unique if exits.
> 

*Proof*  Fix some $g\in D(T^{*})$, suppose $h_{1}$ and $h_{2}$ satisfy $\langle Tf,g\rangle=\langle f,h_{1}\rangle$ and $\langle Tf,g\rangle=\langle f,h_{2}\rangle$ for all $f\in D(T)$. Then, we have $\langle f,h_{1}-h_{2}\rangle=0$ for all $f\in D(T)$. Since $D(T)$ is dense in $\H_{1}$, there exists a sequence $\{x_{n}\}\subset D(T)$ converges to $h_{1}-h_{2}$, which implies that $$\langle x_{n},h_{1}-h_{2}\rangle \to \langle h_{1}-h_{2},h_{1}-h_{2}\rangle=0,$$hence $h_{1}=h_{2}$. $\square$

> [!proposition]
> Suppose $T\colon \H_{1}\to \H_{2}$ and $S\colon \H_{1}\to \H_{2}$ are operators such that $S\subset T$, then $T^{*}\subset S^{*}$.

*Proof*  If $S\subset T$, then $D(S)\subset D(T)$, and $S|_{D(S)}=T|_{D(S)}$. For all $\psi\in D(T^{*})$, we have $\langle T\varphi, \psi\rangle =\langle \varphi, T^{*}\psi\rangle$ for all $\varphi\in D(T)$. So it also holds in $D(S)$, hence $S^{*}\psi=T^{*}\psi$ for all $\psi\in D(T^{*})$. This shows that $\psi\in D(S^{*})$, so $D(T^{*})\subset D(S^{*})$. Therefore, $T^{*}\subset S^{*}$. $\square$

> [!theorem]
> Let $T\colon \H_{1}\to \H_{2}$ be a densely defined operator, then 
> - $T^{*}$ is closed;
> - $T$ is closable if and only if $D(T^{*})$ is dense, in which case $\bar{T}=T^{**}$;
> - If $T$ is closable, then $(\bar{T})^{*}=T^{*}$.
>$\quad$ ^113ce9

*Proof*   For the first statement, suppose $\{f_{n}\}\subset D(T^{*})$ such that $f_{n}\to f$ and $T^{*}f_{n}\to g$, then for all $\varphi\in D(T)$, we have $$\langle T\varphi,f\rangle=\lim_{n\to \infty}\langle T\varphi, f_{n}\rangle=\lim_{n\to \infty}\langle \varphi, T^{*}f_{n}\rangle=\langle \varphi,g\rangle,$$so $f\in D(T^{*})$ and $T^{*}f=g$. This shows that $T^{*}$ is closed.
Now we prove the second statement. Suppose $D(T^{*})$ is dense, then 

> [!definition] Resolvent Set & Resolvent Operator
> Let $T$ be a closed operator on a Hilbert space $\H$. Then the resolvent set of $T$ is defined as $$\rho(T):=\{\lambda\in\C: \lambda\cdot 1-T \colon D(T)\to \H \text{ is bijective with bounded inverse} \}.$$For any $\lambda\in \rho(T)$, the resolvent of $T$ at $\lambda$ is defined as $$R_{\lambda}(T):=(\lambda\cdot 1-T)^{-1}.$$

> [!remark]+
> Note that 


