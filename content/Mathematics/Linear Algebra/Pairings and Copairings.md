> [!definition] Pairing & Copairing
> A *pairing* of two vector spaces $V$ and $W$ over a field $\newcommand{\K}{\mathbb{K}}\K$ is a linear map $\beta\colon V \otimes W \to \K$. It is sometimes convenient to adopt Dirac notation here and write $\beta(v\otimes w)=\braket{v|w}$.
> *Copairing*, as its name suggests, is the dual notion of pairing. That is, a linear map $\gamma\colon \K \to V \otimes W$. It is sometimes convenient to write $\gamma(1)=\sum_{i} v_{i}\otimes w_{i}$. ^concept-3f75522a1827

> [!definition] Nondegenerate Pairing
> A pairing $\beta\colon V\otimes W \to \K$ is called *(left) non-degenerate in $V$* if there exists a copairing $\gamma\colon \K \to W\otimes V$ such that the following composition is the identity map:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/nondegenerate_pairing.svg" style="width:60%;"/>
> Similarly, $\beta$ is called *(right) non-degenerate in $W$* if 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/non_degenerate_pairing_right.svg" style="width:60%;"/>
> is the identity. The pairing $\beta$ is called *non-degenerate* if it is non-degenerate in both $V$ and $W$.
 
> [!remark]
> This might not be the usual definition of nondegeneracy, but we will see that it is equivalent to the usual definition in the finite-dimensional case in a minute.
> 

> [!lemma]
> If a pairing $\beta\colon V\otimes W \to \K$ is non-degenerate, then the two corresponding copairings uniquely agree.
> 

*Proof*  We denote the left copairing by $\gamma_{V}$, and the right copairing by $\gamma_{W}$. Then we have $$\begin{aligned} \gamma_{V}&=(\id_{W} \otimes \id_{V}) \circ \gamma_{V} \\ &= (((\id_{W}\otimes \beta)\circ(\gamma_{W}\otimes \id_{W}))\otimes (\id_{V}\circ \id_{V}))\circ \gamma_{V} \\ &= (\id_{W}\otimes \beta \otimes \id_{V}) \circ (\gamma_{W}\otimes \id_{W}\otimes \id_{V}) \circ \gamma_{V}\\ &= (\id_{W}\otimes \beta \otimes \id_{V}) \circ (\gamma_{W}\otimes \id_{W}\otimes \id_{V}) \circ (\id_{\K}\otimes \gamma_{V}) \\ &= (\id_{W}\otimes \beta \otimes \id_{V}) \circ (\gamma_{W}\otimes \gamma_{V}).   \end{aligned}$$Similarly, we have $\gamma_{W}=(\id_{W}\otimes \beta \otimes \id_{V}) \circ (\gamma_{W}\otimes \gamma_{V})$. Therefore, $\gamma_{V}$ and $\gamma_{W}$ uniquely determine each other. $\square$

> [!remark]+
> This does not mean that left or right non-degeneracy implies the other. For example, let $\beta\colon \R \otimes \R^{2} \to \R$ that maps $z \otimes (x,y) \mapsto zx$, and define a copairing $\gamma\colon \R \to \R^{2} \otimes \R$ by $1 \mapsto (1,0)\otimes 1$. Then $\beta$ is left non-degenerate:
> $$ (\beta\otimes \id_{\R})(\id_{\R}\otimes \gamma)(z) = (\beta\otimes \id_{\R}) (z\otimes (1,0)\otimes 1)= z \otimes 1 =z. $$
> But $\beta$ is right degenerate because no matter what copairing $\gamma'\colon \R \to \R^{2}\otimes \R$ we choose, we have
> $$ (\id_{\R^{2}}\otimes\beta)(\gamma'\otimes \id_{\R^{2}})(0,1)=(\id_{\R^{2}}\otimes\beta)(\gamma'(1) \otimes (0,1))=0\neq(0,1).$$
> 

> [!corollary]
> The obvious evaluation map $$V \otimes V^{*} \to \K, \qquad v \otimes \varphi \mapsto \varphi(v)$$ is nondegenerate if and only if $V$ is of finite dimension.
 
> [!proposition]
> 
> 
