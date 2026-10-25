> [!definition] Pairing & Copairing
> A *pairing* of two vector spaces $V$ and $W$ over a field $\newcommand{\K}{\mathbb{K}}\K$ is a linear map $\beta\colon V \otimes W \to \K$. It is sometimes convenient to adopt Dirac notation here and write $\beta(v\otimes w)=\braket{v|w}$.
> *Copairing*, as its name suggests, is the dual notion of pairing. That is, a linear map $\gamma\colon \K \to V \otimes W$. It is sometimes convenient to write $\gamma(1)=\sum_{i} v_{i}\otimes w_{i}$.

> [!definition] Nondegenerate Pairing
> A pairing $\beta\colon V\otimes W \to \K$ is called *non-degenerate in $V$* if there exists a copairing $\gamma\colon \K \to W\otimes V$ such that the following composition is the identity map:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/nondegenerate_pairing.svg" style="width:60%;"/>
 
> [!remark]
> This might not be the usual definition of nondegeneracy, but we will see that it is equivalent to the usual definition in the finite-dimensional case in a minute.
> 

> [!corollary]
> The obvious evaluation map $$V \otimes V^{*} \to \K, \qquad v \otimes \varphi \mapsto \varphi(v)$$ is nondegenerate if and only if $V$ is of finite dimension.
 
> [!proposition]
> 
> 
