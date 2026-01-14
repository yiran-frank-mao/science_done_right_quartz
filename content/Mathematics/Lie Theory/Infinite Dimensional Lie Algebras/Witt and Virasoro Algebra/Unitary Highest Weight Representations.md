---
cssclasses:
  - img-zoom
tags:
  - conformal-field-theory
---
## Inner Products on Highest Weight Representations

> [!definition] Unitary Highest Weight Representation
> We call a highest weight representation $(\pi, V)$ for $\newcommand{\vir}{\mathfrak{vir}}\vir$ of weight $(h,c)$ *unitary* if there exists a positive definite contravariant  form (i.e., a [[Inner Products#^f0c22c|complex inner product]]) $\left< \cdot,\cdot \right>$ on $V$. In this case, we call $(\pi,V,\left< \cdot,\cdot \right>)$ a *unitary highest weight representation*, in abbreviation *UHW representation*.
>

> [!lemma]
> Suppose $(\pi, V)$ is a $(h,c)$-UHW representation for $\vir$, and $W$ is a submodule of it, then the orthogonal complement $W^{\perp}$ is also a submodule, and both $W$ and $W^{\perp}$ are the direct sum of finite dimensional $L_{0}$-eigenspaces.

*Proof*  For any $v\in W^{\perp}$, $w\in W$ and $n\in\Z$, we have $$\langle \pi(L_{n})v,w\rangle=\langle v,\pi(L_{n})^{*}w\rangle=\langle v,\pi(L_{-n})w\rangle=0,$$so $\pi(L_{n})v\in W^{\perp}$. Hence, $W^{\perp}$ is a submodule. Since $L_{0}$ is diagonalizable on $V$, $W$ is the direct sum of finite dimensional spaces $W\cap V_{h+k}$, for $V_{h+k}$ being eigenspaces of $L_{0}$. $\square$

> [!proposition]
> If $(V,v_{0})$ is a pointed UHW representation of weight $(h,c)$, then the submodule $U(\vir) v_{0}$ is irreducible and isomorphic to $L(h,c)$. ^a789b2

*Proof*  In the category $\newcommand{\HW}{\mathbf{HW}_{h,c}^{\bullet}}\HW$, $\newcommand{\ver}{\mathcal{V}_{h,c}}(\ver, 1_{U(\vir)}\otimes 1_{\C})$ is the initial object. So there exists $\Phi_{V}\colon (\ver, 1_{U(\vir)}\otimes 1_{\C}) \to (V,v_{0})$. Notice that $$\newcommand{\im}{\mathrm{im}\,}\begin{aligned}U(\vir) \cdot v_{0} &= \Phi_{V}\left(U(\vir)\cdot 1_{U(\vir)}\otimes 1_{\C}\right)= \left\{ \Phi_{V}(x \otimes 1_{\C}) \mid  x\in U(\vir) \right\}=\im \Phi_{V}\end{aligned},$$so $U(\vir) \cdot v_{0}\cong \ver / \ker \Phi_{V}$. Moreover, suppose $W\subsetneq U(\vir) \cdot v_{0}$ is a proper submodule, then $v_{0}\notin W$, so $v_{0}\in W^{\perp}$. Hence, $W^{\perp} \cap U(\vir)v_{0}=U(\vir) v_{0}$, thus $$W\subset U(\vir)v_{0}\subseteq W^{\perp}.$$It follows that $W=\{0\}$, so $U(\vir)v_{0}$ is irreducible. As $L(h,c)$ is the only irreducible quotient of $\ver$, we have $U(\vir)v_{0}\cong L(h,c)$. $\square$

A direct consequence of the above proposition is that the contravariant form on $V$ can be restricted to $L(h,c)$:

> [!corollary]
> If $(\pi, V,\left< \cdot,\cdot \right>)$ is a UHW representation for $\vir$, then $\left< \cdot,\cdot \right>$ restricts to a positive multiple of the contravariant form on $L(h,c)$.

> [!corollary]
> Any $(h,c)$-UHW representation $(\pi, V)$ is completely reducible.
> Moreover, if $(\pi_{n},V)$ is the representation of $\newcommand{\sl}{\mathfrak{sl}}\sl_{2}(\C)$ induced by $(\pi,V)$, then it is completely reducible as well.

*Proof*  We first show that $(\pi, V)$ can be decomposed into irreducible modules of $\vir$ through a recursive process, and then the same process will work for $(\pi_{n},V)$. From the [[unitary Highest Weight Representations#^a789b2|above proposition]], we know that $U(\vir)v_{0}$ is a irreducible submodule for $v_{0}\in V$ being the highest weight vector. $V$ can be decomposed into direct sum of irreducible submodules by the following procedure defined recursively:
1. Pick some highest weight $v_{0}\in V$, then $W=U(\vir)v_{0}$ is an irreducible submodule. Let $V_{1}:=W^\perp$, which is also a submodule.
2. If $V_{1}=\{0\}$, then stop. Otherwise, apply the same procedure on $V_{1}$.

This algorithm must terminate at each energy level, because each $L_{0}$-eigenspaces is finite dimensional, and taking the orthogonal sum over all levels (countably many) exhausts $V$. $\square$

## Quantization

> [!theorem] Friedan–Qiu–Shenker Classification
> An $(h,c)$-highest weight representation $(\pi,V)$ for $\vir$ is unitary if and only if either $c\geq 1$ and $h\geq 0$ or
> $$c=1-\frac{6}{m(m+1)},\quad\text{and}\quad h=\frac{((m+1)r-ms)^{2}-1}{4m(m+1)},$$
> for some integers $m\geq 2$, $1\leq s\leq r\leq m-1$. In particular, $c\geq {0}$ and $h\geq 0$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/Friedan–Qiu–Shenker_classification.svg" alt="https://colab.research.google.com/drive/1VS1hO6PE_BWg3OOqn4JPkUYy8bahirjr?usp=drive_link" style="width:80%;"/>

*Proof*  See [[unitary Highest Weight Representations#^bd6e39|Ref.1]]. $\square$

## Energy Bounds

> [!lemma]
> Fix a UHW representation $(\pi, V)$ of $\vir$. Suppose $W \subset V$ containing some vector $v$ such that $\pi|_{W}$ is an irreducible HW representation of $\mathfrak{sl}_{2}(\C)$, and there exists $a \ge 1$ such that $(I+\pi(L_{0}))v=a v$. Then for all $n\in\Z$, $$\| \pi(L_{n})v \|\leq \left( \sqrt{2}a + \sqrt{\frac{c}{12}} (1+|n|)\sqrt{a} + \sqrt{2}|n|\sqrt{a} +\sqrt{\frac{c}{12}} (1+|n|)^{3/2} \right) \|v\|.$$
> Moreover,
> $$\|\pi(L_{n})v\|_{-1}\leq \sqrt{2}\|L_{n}\|_{1}\|v\|_{1}+\sqrt{\frac{c}{12}}\|L_{n}\|_{3/2}\|v\|+\left(\sqrt{2}+\sqrt{\frac{c}{12}}\right)\|L_{n}\|_{5/2}\|v\|_{-1}.$$

*Proof*  We use the standard basis $\{H,E,F\}$ of $\sl_{2}(\C)$. Fix some $n\geq 0$, since $(\pi_{n}|_{W},W)$ is an irreducible HW representation of $\sl_{2}(\C)$, we can write $$\newcommand{\span}{\mathrm{span}}W=\span\{F^{m}v \mid m \in \Z_{\geq_{0}}\}.$$Let $p$ be the highest weight of $\pi_{n}(H)$ on $W$. Then applying the commutation relation $[H,F^{m}]=F^{m}H-2mF^{m}$ gives us $\pi_{n}(H)v=(p-2m)v$ for some $m \in \mathbb{Z}_{\ge 0}$. Note that the [[General and Special Linear Groups#^4c1fe6|Casimir operator]] $\Omega=\frac{1}{2}H^{2} + EF+FE$ lies in the center of $\sl_{2}(\C)$, so it acts as a scalar multiplication. Note that $$\pi_{n}(\Omega) w_{0}=\left(\frac{1}{2}p^{2}+p\right)w_{0}$$for any highest weight vector $w_{0}\in W$ of $(\pi_{n}|_{W},W)$, thus $\Omega$ acts as multiplying by $\frac{1}{2}p^{2}+p$ on the whole $W$, in particular, $\pi_{n}(\Omega) v=(\frac{1}{2}p^{2}+p)v$. Therefore, substituting $\pi_{n}(H)v=(p-2m)v$ into this equation gives us $$\pi_{n}\left(\frac{1}{2}H^{2}+H+2FE\right)v=\pi_{n}\left(\frac{1}{2}(p-2m)^{2}+(p-2m)+2FE\right)v,$$it follows that $$\pi_{n}(FE)v=m(p+1-m)v.$$Therefore, $$\|\pi_{n}(E)v\|^{2} = \langle \pi_{n}(E) v, \pi_{n}(E)v\rangle = -\langle \pi_{n}(FE)v, v\rangle = -m(p+1-m)\|v\|^{2}.$$As $\pi_{n}(E)=-\frac{i}{n}\pi(L_{n})$, it further deduces to $$\|\pi(L_{n})v \|^{2}=nm(nm-np-1)\|v\|^{2}.$$Now since $\pi_{n}(H)v=(p-2m)v$, we have $\left(-\frac{2}{n}\pi(L_{0})-\frac{n^{2}-1}{12n}c\right) v = (p-2m)v$. By our assumption that $v$ is an eigenvector of $I+\pi(L_{0})$, we have $\pi(L_{0}) v= (a-1)v$, hence, $$-2(a-1)-\frac{n^{2}-1}{12}c=np-2nm.\tag{1}$$Now, notice that a highest weight vector $w_{0}$ is also a vector in $V$, so $w_{0}$ is in some $(h+k)$-eigenspace for $k\in\N$, that is $p w_{0} = \left(-\frac{2}{n}\pi(L_{0}) - \frac{n^{2}-1}{12n}c\right)w_{0}$, so $$np = \left(-2(h+k) - \frac{n^{2}-1}{12}c\right).\tag{2}$$Subtracting this from $(1)$, we get $$nm=-(h+k)-1+a.$$Since $h\geq 0$ and $mn\geq 0$, the above equation implies that $$mn\leq a-1,\quad h+k\leq a-1.\tag{3}$$Similarly, adding $(1)$ and $(2)$, $$nm-np=a-1+h+k+\frac{n^{2}-1}{12}c\leq 2a-2 + \frac{n^{2}-1}{12}c\leq 2a+ \frac{n^{2}-1}{12}c.$$As a result, $$\|\pi(L_{n})v \|^{2}=nm(nm-np-1)\|v\|^{2}\leq (a-1)\left( 2a+ \frac{n^{2}-1}{12}c \right) \|v\|^{2}\leq\left( 2a^2+ \frac{n^{2}-1}{12}ca \right) \|v\|^{2}.\tag{4}$$By the commutation relation $[L_{n},L_{-n}]=2nL_{0}$, one can derive that $$\begin{aligned}\|\pi(L_{-n})v\|^{2} &= \langle \pi(L_{-n})v,\pi(L_{-n})v \rangle \\ &= \langle \pi(L_{n}) \pi(L_{-n}) v, v \rangle\\ &= \langle \pi([L_{n},L_{-n}])v,v \rangle+\langle \pi(L_{-n})\pi(L_{n})v,v \rangle +\frac{n(n^{2}-1)}{12}c\|v\|^{2} \\ &= \left( 2n(a-1)+\frac{n(n^{2}-1)}{12}c \right) \|v\|^{2} + \|\pi(L_{n})v\|^{2}. \end{aligned}$$Together with $(4)$, this gives the basic estimate $$\| \pi(L_{n})v \|\leq \left( \sqrt{2}a + \sqrt{\frac{c}{12}} (1+|n|)\sqrt{a} + \sqrt{2}|n|\sqrt{a} +\sqrt{\frac{c}{12}} (1+|n|)^{3/2} \right) \|v\| $$for all $n\in \Z$.
To show the second estimate, we first observe that if $n>a-1$, then $(3)$ implies that $m<1$, as $m$ is nonnegative, $m=0$, so $\pi(L_{n})d=0$. So we may assume without loss of generality that $n\leq a-1$. Note that $$(I+\pi(L_{0}))\pi (L_{n})v = (a-n) \pi(L_{n})v,$$so by functional calculus, $(I+\pi(L_{0}))^{-1/2}\pi (L_{n})v = (a-n)^{-1/2} \pi(L_{n})v$. Hence, $$\| \pi(L_{n})v \|_{-1}\leq (a-n)^{-1/2} \left( \sqrt{2}a + \sqrt{\frac{c}{12}} (1+|n|)\sqrt{a} + \sqrt{2}|n|\sqrt{a} +\sqrt{\frac{c}{12}} (1+|n|)^{3/2} \right) \|v\|. $$Case $n<0$, then $a-n\geq a$, so $(a-n)^{-1/2}\leq a^{-1/2}$.
Case $n\geq 0$, then $(a-n)^{-1/2}\leq a^{-1/2} (1+|n|)^{-1/2}$.
Substituting these bounds into the initial inequality yields the desired estimate for both cases, completing the proof.  $\square$

> [!remark]+
> The above proof closely follows the original argument of [[unitary Highest Weight Representations#^9b91ee|Goodman and Wallach (1985)]]. However, it is worth noting that there appears to be a minor typo in their equation (2.8): a term of the form $2n(a-1)\|v\|^{2}$ seems to be missing. This omission has been corrected in the version presented here. The discrepancy is ultimately harmless for our purposes, since we only require the expression to be bounded by a polynomial, and the conclusion remains unaffected.

> [!lemma]
> Fix a UHW representation $(\pi, V)$ of $\vir$. For all $\newcommand{\witt}{\mathfrak{witt}}X\in\witt$ and $v\in V$,
> $$\|\pi(X)v\|_{-1}\leq \sqrt{2}\|X\|_{1}\|v\|_{1}+\sqrt{\frac{c}{12}}\|X\|_{3/2}\|v\|+\left(\sqrt{2}+\sqrt{\frac{c}{12}}\right)\|X\|_{5/2}\|v\|_{-1}.$$
>

*Proof*  Every $X\in\witt$ in the Witt is a finite linear combination of generators $\{L_{n}\}_{n\in\Z}$, so the triangle inequality guarantees that the inequality holds for all $X$. Furthermore, $I+\pi(L_{0})$ is self-adjoint with discrete spectrum, so any $v\in V$ can be decomposed into eigenvectors of  $I+\pi(L_{0})$, and we have proved the desired inequality for each eigenvector, so it holds for all $v\in V$. $\square$

> [!theorem]
> If $(\pi, V, \langle \cdot,\cdot\rangle)$ is a UHW representation of $\vir$, then it can be extended to a continuous projective representation $\newcommand{\H}{\mathcal{H}}(\tilde{\pi},\H)$ of $\mathfrak{d}_{\infty}$, such that $$\langle \pi(X)v,w \rangle = \langle v, \pi(X^{*}) w\rangle$$
> for all $v\in\H^{\infty}$ and $w\in \H^{-\infty}$, where $\H$ is the [[Complete Metric Space#^67b510|completion]] of $V$ with respect to $\left< \cdot,\cdot \right>$, and $\{\newcommand{\H}{\mathcal{H}}\H^{t}\}_{t\in\R}$ are [[Nelson's Commutator Theorem#^eec324|scales]] of $\H$ associated with $A:=\overline{\pi(L_{0})}$.
> In particular, if $X\in\mathfrak{d}_{\infty}$ and $X^{*}=X$, then $\pi(X)$ is [[Symmetric and Self-Adjoint Operators#^e5fbca|essentially self-adjoint]] as a unbounded operator on $\H$.

*Proof*  By the above lemma, since $\|\pi(X)v\|$ is bounded, it can be extended to $\mathfrak{d}_{\infty}$. Fix a UHW representation $(\pi, V)$ for $\vir$ of weight $(h,c)$. let $A:=\overline{\pi(L_{0})}$, then $\H^t$ is a [[Hilbert Spaces#^ae0212|Hilbert space]] with inner product $$\langle v,w\rangle_{t}: = \langle (A+I)^{t/2}v, (A+I)^{t/2} w  \rangle.$$From the above estimate, we know that $$\|\pi(X)v\|_{-1}\leq C_{1} \|v\|_{1} +C_{2}\|v\|+C_{3}\|v\|_{-1}.$$Recall that $\| v \|_{1}\geq \|v\| \geq \| v \|_{-1}$ (ref. [[Nelson's Commutator Theorem#^af59cb|proposition]]), so $\newcommand{\L}{\mathscr{L}}\pi(X)\in \L_{0}(\H^{1}, \H^{-1})$. Note that $$[A,\pi(L_{n})]=[\pi(L_{0}),\pi(L_{n})]=-n\pi(L_{n}),$$so $[A,\pi(X)]\in \L_{0}(\H^{1}, \H^{-1})$ as well. In particular, if $X=X^{*}$, then $$\langle v, \pi(X)w \rangle=\langle \pi(X)v,w \rangle=\langle \pi(X)v,w \rangle_{-1,1}=\langle v, \pi(X)^{\dagger}w \rangle_{1,-1}=\langle v, \pi(X)^{\dagger} w \rangle,$$thus $\pi(X)^{\dagger}=\pi(X)$, $\pi(X)$ is [[Nelson's Commutator Theorem#^c1eb50|formally Hermitian]], so it is essentially self-adjoint by [[Nelson's Commutator Theorem#^edbb20|Nelson's commutator theorem]]. $\square$

[[Stone's Theorem#^61f239|Stone's theorem]] immediately implies the following corollary:

> [!corollary]
> Suppose $X$ is a real [[Vector Fields and Lie Algebra#^a87ff1|vector field]] on $S^{1}$. Then $e^{t \overline{\tilde{\pi}(X)}}$ is a strongly continuous one-parameter group of unitary operators on $\H$.

## References

[Details of the non-unitarity proof for highest weight representations of the Virasoro algebra](https://doi.org/10.1007/BF01205483) ^bd6e39

[Goodman and Wallach, Projective unitary positive-energy representations of $\mathrm{Diff}(S^1)$](https://linkinghub.elsevier.com/retrieve/pii/0022123685900904) ^9b91ee
