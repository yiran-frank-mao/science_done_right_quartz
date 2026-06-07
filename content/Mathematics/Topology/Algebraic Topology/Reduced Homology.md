---
created: 2025-09-22
updated: 2025-09-22
tags:
  - algebraic-topology
  - homology
completed: true
---
## Reduced Homology and Path Components

Recall that the singular homology of a point is:

![[Singular Homology#^f1d145]]

It is often convenient to modify the definition of homology so that a point has trivial homology in all dimensions. This leads to reduced homology.

> [!definition] Reduced Homology
> The *reduced singular homology groups*, denoted $\tilde{H}_n(X)$, are the homology groups of the *augmented chain complex*:
> $$ \dots \to C_1(X) \xrightarrow{d_1} C_0(X) \xrightarrow{d_{0}} \mathbb{Z} \to 0, $$
> where the *augmentation map* $d_{0}\colon C_0(X) \to \mathbb{Z}$ is defined by $d_{0}\left(\sum n_i \sigma_i\right) = \sum n_i$.

> [!remark]-
> This definition makes sense, since $\Delta^{-1}$ can be recognized as the empty set, and there is a unique map from the empty set to any space, so $C_{-1}(X) \cong \mathbb{Z}$.

<u><b>e.g.</b></u>  For a point, the augmentation map $d_{0}\colon C_0(\{*\}) \to \mathbb{Z}$ is an isomorphism, which makes the augmented complex exact. Thus the reduced homology of a point is trivial in all dimensions: $$ \tilde{H}_n(\{*\}) = 0 \quad \text{for all } n \ge 0. $$

> [!proposition] 
> Let $\newcommand{\Z}{\mathbb{Z}}X$ be a non-empty, [[Connectedness and Paths#^630354|path-connected]] space. Then $H_0(X) \cong \Z$ and $\tilde{H}_0(X) = 0$.

*Proof*  The map $d_{0}\colon C_0(X) \to \Z$ is surjective since $X \neq \emptyset$. The first isomorphism theorem tells that $H_{0}(X)\cong \Z$ iff $\tilde{H}_{0}(X)\cong 0$, so it's sufficient to show $\tilde{H}_0(X) = 0$.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/reduced_0homology_of_PC_space.svg" alt="reduced_0homology_of_PC_space" style="width:32%;"/>
From the above diagram, we know that the reduced homology $\tilde{H}_0(X)$ is the kernel of the induced map $\bar{d}_{0}\colon H_0(X) \to \Z$. Let $[\alpha] \in \tilde{H}_0(X)$, where $\alpha = \sum n_i x_i$ is a 0-cycle. The condition for $[\alpha]$ to be in the kernel is that $d_{0}(\alpha) = \sum n_i = 0$. Since $X$ is path-connected, for any two points $x_i, x_j \in X$, there exists a path $\sigma\colon [0,1] \to X$ from $x_j$ to $x_i$. This path is a 1-simplex, and its boundary is $\partial_1(\sigma) = x_i - x_j$. Because $\sum n_i = 0$, we can express $\alpha$ as a sum of terms like $(x_i - x_0)$, and each of these is the boundary of a path from $x_0$ to $x_i$. Therefore, $\alpha$ is a boundary, which means $[\alpha] = 0$ in $H_0(X)$. Thus, $\tilde{H}_0(X) = 0$. $\square$

## Homology of Disjoint Unions

> [!definition] Direct Sum of Chain Complexes
> If $C$ and $D$ are chain complexes, then their *direct sum* $C\oplus D$ is the chain complex with $(C\oplus D)_{n}:=C_{n} \oplus D_{n}$, and the boundary map defined by $d_{n}(x,y) = (d_{n}(x), d_{n}(y))$.

> [!lemma]
> The following properties hold:
> - $C_{*}(X \sqcup Y)\cong C_{*}(X) \oplus C_{*}(Y)$,
> - $H_n(C \oplus D) \cong H_n(C) \oplus H_n(D)$, moreover, $H_{n}(X\sqcup Y)\cong H_{n}(X)\oplus H_{n}(Y)$.
> $\quad$

> [!corollary]
> If a space $X$ is a disjoint union of its path components $X_\alpha$, then the homology groups are direct sums:
> $$H_n(X) \cong \bigoplus_{\alpha} H_n(X_\alpha)$$
> In particular, for any space $X$, $H_{0}(X)\cong \bigoplus_{\alpha}X_{\alpha}$ counts the number of path-components of $X$.

