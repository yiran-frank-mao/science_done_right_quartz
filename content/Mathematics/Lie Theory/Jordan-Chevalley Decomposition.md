## Decomposition
 
 > [!theorem] Jordan-Chevalley Decomposition
> Let $V$ be a finite dimensional [[Vector Spaces#^f4b63e|vector space]] over an [[Fields Construction#^5b9555|algebraically closed]] [[Ring, Field and Integral Domain#^575174|field]] $F$. Let $\newcommand{\End}{\operatorname{End}}x \in \End(V)$. Then:
> 1. There exists a unique pair $x_{s}, x_{n} \in \operatorname{End}(V)$ such that:
> 	- $x_{s}$ is semisimple (i.e., diagonalisable)
> 	- $x_{n}$ is nilpotent
> 	- $\left[x_{s}, x_{n}\right]=0$
> 	- $x=x_{s}+x_{n}$
> 
> 2. There exists polynomials $p, q \in F[t]$ such that $p(0)=q(0)=0, x_{s}=p(x)$ and $x_{n}=q(x)$.
> 3. For all $y \in \operatorname{End}(V)$, if $[x, y]=0$, then $\left[x_{s}, y\right]=\left[x_{n}, y\right]=0$.
> 4. If $A \subset B \subset V$ with $x \cdot B \subset A$, then $x_{s} \cdot B \subset A$ and $x_{n} \cdot B \subset A$.
> $\quad$ ^caa6cd

*Proof*  Since $F$ is algebraically closed, then the characteristic polynomial of $x$ is of the form: $$\chi_{x}(t)=\prod_{i=1}^{k}\left(t-a_{i}\right)^{m_{i}} \in F[t]$$where $a_{1}, \ldots, a_{k}$ are the distinct eigenvalues of $x$. Denote the generalised eigenspaces of $x$ by $V_{i}=\ker\left(x-a_{i} I\right)^{m_{i}}$. Let $I_{i}=\left(t-a_{i}\right)^{m_{i}} \triangleleft F[t]$. For $i \neq j$ we have that $I_{i}$ and $I_{j}$ are coprime, then by the [[Homomorphisms and Ideals#^27e653|Chinese Remainder Theorem]],$$\exists p \in F[t] \text { such that } p \equiv a_{i} \bmod \left(t-a_{i}\right)^{m_{i}} \text { for } i=1, \ldots, k$$
We also require that $p \equiv 0 \bmod t$, noting that this is redundant if $0$ is an eigenvalue.
Define $q(t)=t-p(t)$. So $p(0)=q(0)=0$. Define $x_{s}=p(x)$ and $x_{n}=q(x)$. We claim that these have the desired properties. Indeed, $x=x_{s}+x_{n}$, because$$x_{s}+x_{n}=p(x)+q(x)=p(x)+x-p(x)=x.$$Furthermore, $x_{s}$ and $x_{n}$ are polynomials in $x$, and therefore commute with each other and with anything that commutes with $x$. If $A \subset B \subset V$ with $x \cdot B \subset A$, then the same hold by replacing $x$ with a polynomial in $x$, in particular this is true for $x_{s}$ and $x_{n}$.
We need to show that $x_{s}$ is semisimple and $x_{n}$ is nilpotent. Recall that when $x$ acts on $V$, it splits into its generalised eigenspaces $V_{i}$ as above with $V=V_{1} \oplus \cdots \oplus V_{k}$, preserving each as $x: V_{i} \rightarrow V_{i}$. Therefore: $$\begin{aligned}& p(t) \equiv a_{t} \quad \bmod \left(t-a_{t}\right)^{m_{t}} \\& \Longrightarrow x_{s} \equiv a_{t} I \quad \bmod \left(x-a_{t}I\right)^{m_{t}} V \\& \Longrightarrow\left.x_{s}\right|_{V_{i}}=\left.a_{t} I\right|_{V_{i}}\end{aligned}$$and thus $x_{s}$ acts as a scalar on each of the eigenspaces $V_{i}$. Therefore, $x_{s}$ is semisimple.
On each space $V_{i}, x$ has generalised eigenvalue $a_{i}$ and $x_{s}$ has eigenvalue $a_{i}$ as above; hence, on every $V_{i}, x_{n}=x-x_{s}$ has generalised eigenvalue 0 . Therefore it is nilpotent.
Finally, we must also show that $x_{s}$ and $x_{n}$ are unique. Suppose that $x=s+n$ for some semisimple $s$ and nilpotent $n$ with $[s, n]=0$. Then, since $x=x_{s}+x_{n}$, we have:$$x_{s}-s=x_{n}-n$$The LHS is a sum of commuting semisimple operators, because they commute with $x$ and therefore commute with any operator that commute with $x$, so is semisimple. By the same reasoning the RHS is a sum of commuting nilpotent operators, so is nilpotent. It follows that $x_{s}-s=x_{n}-n$ is semisimple and nilpotent: so it is diagonalisable, but with all eigenvalues equal to 0 ; hence it is the zero operator. That is, $x_{s}-s=x_{n}-n=0$, so $x_{s}=s$ and $x_{n}=n$. $\square$

> [!proposition]
> If $x \in \operatorname{End}(V)$ is semisimple so is $\operatorname{ad}_{x}$, and similarly, if $x$ is nilpotent so is $\operatorname{ad}_{x}$. 
> Furthermore, if $x=s+n$ is a Jordan-Chevalley decomposition in $\operatorname{End}(V)$ then $\operatorname{ad}_{x}=\operatorname{ad}_{s}+\operatorname{ad}_{n}$ is a Jordan-Chevalley decomposition in $\operatorname{End}(\operatorname{End}(V))$.
> 

*Proof*  Since $s$ is semisimple, $V$ has an eigenbasis $\{v_{i}\}_{i=1}^{n}$ with eigenvalues $\lambda_{i}$. A basis for $\End(V)$ is given by $\varphi_{ij}(v_{k})=\delta_{k,j}v_{i}$. Then $$\newcommand{\ad}{\operatorname{ad}}\ad_{s}(\varphi_{ij})(v_{k})=(s\varphi_{ij}-\varphi_{ij}s)v_{k}=\delta_{k,j}(\lambda_{i}-\lambda_{k})v_{i}=(\lambda_{i}-\lambda_{k})\varphi_{i,j}(v_{k}),$$so $\ad_{s}$ diagonalizes in this basis, hence is semisimple. $\ad_{n}$ is nilpotent by the [[Engel's Theorem#^818119|lemma]]. Since $\ad$ is a Lie algebra homomorphism, the polynomial relations are preserved. Finally, the Jordan-Chevalley decomposition is unique, so  $\ad_{x}=\ad_{s}+\ad_{n}$ is the Jordan-Chevalley decomposition of $\ad_{x}$. $\square$

The above decomposition can be pulled back to any semisimple Lie algebras through the adjoint representation:

> [!theorem] Abstract Jordan-Chevalley Decomposition
> Let $\newcommand{\g}{\mathfrak{g}}\g$ be a [[Ideals, Simple and Semisimple Lie Algebras#^476cc0|semisimple]] Lie algebra over an [[Fields Construction#^5b9555|algebraically closed]] field. For $x \in \mathfrak{g}$ let $\operatorname{ad}_{x}=S+N$ be the Jordan decomposition of $\operatorname{ad}_{x}$ in $\operatorname{End}(\mathfrak{g})$. Then, there exist unique $s, n \in \mathfrak{g}$ such that $\operatorname{ad}_{s}=S$ and $\operatorname{ad}_{n}=N$. The decomposition $x=s+n$ in $\mathfrak{g}$ is called the *abstract Jordan-Chevalley decomposition*. ^245420

> [!theorem]
> For semisimple Lie algebras, the Jordan–Chevalley decomposition is preserved by all finite-dimensional representations. That is, if $\g$ is semisimple and $x \in \g$ is ad-semisimple, then $\rho(x) ∈ \End(V)$ is semisimple in any finite dimensional representation $(\rho,V)$ of $\g$. ^cd64a6
