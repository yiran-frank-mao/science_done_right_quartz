## Distribution and Frobenius Theorem

> [!definition] Distribution
> Given a smooth manifold $M$, a distribution $\mathcal{D}$ of $k$-planes on $M$ is a [[Vector Bundles#^c5246b|subbundle]] of the [[Tangent Vectors and Spaces#^e3492e|tangent bundle]] $TM$, such that for each $p\in M$, the [[Vector Bundles#^9cb683|fiber]] is a $k$-dimensional linear subspace of $T_{p}M$.

> [!definition] Integrable Distribution
> A distribution $\mathcal{D}$ of $k$-planes is integrable if for all $p\in M$, there exists a nonempty immersed submanifold $\Sigma$ in $M$ of dimension $k$ containing $p$ such that $\mathcal{D}(p)=T_{p}\Sigma$.

> [!theorem] Frobenius Theorem
> A distribution $\mathcal{D}$ of $k$-planes on $M$ is integrable if and only if the space of vector fields along $\mathcal{D}$, i.e. $\{V\in\mathfrak{X}(M): \forall x\in M, V(x)\in\mathcal{D}(x)\}$ is a (sub) [[Vector Fields and Lie Algebra#^5007ba|Lie algebra]] closed under the [[Vector Fields and Lie Algebra#^beba98|Lie bracket]] operation. In other words, $\mathcal{D}$ is involutive.

> [!corollary] 
> Suppose $M$ is a smooth manifold, $\mathcal{D}$ is an involutive $k$-plane distribution on $M$, and $S \subseteq M$ is a codimension-$k$ [[Manifolds and Atlases#^632f7d|embedded submanifold]]. If $p \in S$ is a point such that $T_p S$ is complementary to $\mathcal{D}_p$, then there is a flat chart $(U, (s^i))$ for $\mathcal{D}$ centered at $p$ in which $S \cap U$ is the slice $s^1 = \cdots = s^k = 0$.

> [!corollary] Alternative Form of Frobenius Theorem
> Let $\mathcal{D}$ be a $k$-dimensional, involutive distribution on a smooth $n$-manifold $M$. Let $p \in M$. Then there exists an integral manifold of $\mathcal{D}$ passing through $p$. Indeed, there exists a cubic coordinate system $(U,\phi)$ which is centered at $p$, with coordinate functions $x^{1}, \dots, x^{n}$ such that the slices
> $$ x^{i} = \text{constant} \quad \text{for all } i \in \{k+1, \dots, n\} $$
> are integral manifolds of $\mathcal{D}$; and if $(N,\psi)$ is a connected integral manifold of $\mathcal{D}$ such that $\psi(N) \subset U$, then $\psi(N)$ lies in one of these slices.

## Foliations

> [!definition] Foliation
> Let $M$ be an $n$-dimensional manifold. A $k$-dimensional foliation is a decomposition of $M$ as a disjoint union of connected immersed submanifolds of $M$: $$M = \bigsqcup_{\alpha\in A}  L_{\alpha} $$where each $L_{\alpha}$ is called a leaf, and the following condition is satisfied:
> Every point $p\in M$ has a neighbourhood $U$ and a local chart $\varphi\colon U\to \R^{n}$ such that for each leaf $L_{\alpha}$, $L_{\alpha}\cap U$  is described by the level sets of $\varphi$. That is, $\varphi(L_{\alpha}\cap U)=\{x\in \R^{n}\mid x^{k+1}=c_{1},\dots,x^{n}=c_{n}\}$, where $c_{1},\dots c_{n}$ are real constants.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/foliation_definition.svg" alt="foliation_definition" style="width:55%;"/>
>  ^4c94fb
