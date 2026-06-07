In [[The Integrability Theorem|the integrability theorem]], we demonstrated that every projective representation of $\newcommand{\C}{\mathbb{C}}\mathfrak{X}_{\C}(S^{1})$ integrates to a projective representation of $\Diff^{+}(S^{1})$, and so does $\mathfrak{X}_{\R}(S^{1})$. This result initially appears paradoxical, as one might expect a real Lie algebra to integrate to a real Lie group, with its complexification integrating to the complexification of that group. However, this expectation is not met here, as $\Diff^{+}(S^1)$ lacks a complexification. Instead, an "almost" complexification of it is a semigroup of annuli.

## $\Diff^+(S^1)$ Cannot be Complexified

> [!theorem]
> $\Diff^+(S^1)$ does not admit a complexification.
> 

*Proof*  We can see this by contradiction. If there were a complex Lie group $G$ serving as the complexification, then 

## The Semigroup of Annuli

> [!definition] Semigroup of Annuli
> The *semigroup of annuli*, denoted $\newcommand{\Ann}{\mathrm{Ann}}\Ann$, consists of equivalence classes of triples $\newcommand{\phiin}{\gamma_{-}}\newcommand{\phiout}{\gamma_{+}}(\Sigma, \phiin, \phiout)$ where $\Sigma$ is a Riemann surface biholomorphic to an annulus, and $\phiin\colon S^{1}\to \partial_{-}\Sigma$, $\phiout\colon S^{1}\to \partial_{+} \Sigma$ are parametrizations of the inner and outer boundary components of $\Sigma$, respectively. Both $\phiin$ and $\phiout$ are orientation-preserving smooth diffeomorphisms onto their images.
> Two annuli $(\Sigma, \phiin, \phiout)$ and $(\Sigma', \phiin', \phiout')$ are considered equivalent if there exists a biholomorphic map $f\colon \Sigma\to \Sigma'$ such that $f\circ \phiin = \phiin'$ and $f\circ \phiout = \phiout'$.
> The semigroup operation is defined by sewing annuli along their boundaries. Given two annuli $(\Sigma, \phiin, \phiout)$ and $(\Sigma', \phiin', \phiout')$, their product is obtained by identifying the outer boundary of $\Sigma$ with the inner boundary of $\Sigma'$ via the parametrizations $\phiout$ and $\phiin'$. The resulting annulus is $(\Sigma\sqcup \Sigma' / \phiin'(e^{i\theta})\sim\phiout(e^{i\theta}), \phiin,\phiout')$, and we shall simply denote it by $\Sigma\cdot \Sigma'$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/some_annulus.svg" alt="some_annulus" style="width:55%;"/> 
> 

> [!remark]+
> What we really care about here is not the plain annuli, but the rigged annuli that including the parametrisation information of the boundaries (riggings). If you forget the boundary parametrisations and look only at conformal isomorphism classes of annuli, then every annulus is conformally equivalent to a round annulus $A_{t}=\{z:e^{-t}<∣z∣<1\}$, and its conformal type is determined by a single real number $t$. 

Clearly, the welding of two annuli remains an annulus topologically, we need to verify that the resulting annulus can be given a complex structure. This is, in fact, a [[Topological Gluing|topological gluing]] with extra conformality, and will be discussed in [[Conformal Welding Problem|conformal welding problem]].
Once we checked that $\Ann$ is a well-defined semigroup, for any $[(\Sigma,\gamma_{-},\gamma_{+})]\in \Ann$, we can pick a standard representative, i.e., a round annulus $\newcommand{\bgamma}{\bar{\gamma}}(A_{t}, \bgamma_{-},\bgamma_{+})​$ $(t>0)$ such that $\bgamma_{-}(1)=1$ and $\bgamma_{+}(1)=1$.
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/Round_annulus.svg" alt="Round_annulus" style="width:50%;"/>

> [!proposition]
> $\Ann$ is an complex Fréchet manifold, inheriting the complex structure from $C^{\infty}(S^{1})\oplus C^{\infty}(S^{1})$.
> 

*Proof*  It suffices to show that the inclusion $\iota\colon \Ann\to C^{\infty}(S^{1})\times C^{\infty}(S^{1})$ has an open image. 

> [!definition] Involution on $\Ann$
> There is an involution $*\colon \Ann \to \Ann$ that turns an annulus inside out, so that the incoming and outgoing circles are exchanged, but their parametrizations remain the same
> 

## Alternative Realization of $\Ann$

We shall introduce two more realizations of elements in $\Ann$ here, and see how $\Diff^{+}(S^{1})$ can be embedded as the boundary of $\Ann$, so that $\overline{\Ann}:=\Ann \cup \Diff^{+}(S^{1})$ is a complex manifold with boundary and a monoid.

> [!proposition] 
> Every annulus can be uniquely (up to some normalization) identified as a tuple $(S, \Phi^{-}, \Phi^{+})$, where $S$ is a Riemann surface conformally equivalent to the Riemann sphere, and $\Phi^{-}\colon D_{-}\to S\setminus \Phi^{+}(D_{+})$ and $\Phi^{+}\colon D_{+}\to S\setminus \Phi^{-}(D_{-})$ are holomorphic embeddings of the unit disk $D_{-}=\{z\in \C: |z|<1\}$ and $D_{+}=\{z\in \C: |z|>1\}$.
>  
 
*Proof*  This is a direct result of the conformal welding. For each annulus $(\Sigma, \gamma_{-}, \gamma_{+})$, we can weld an upper disk to its inner boundary and a lower disk to its outer boundary, so that the resulting Riemann surface is conformally equivalent to the Riemann sphere. The holomorphic embeddings $\Phi^{-}$ and $\Phi^{+}$ are given by the $\gamma_{-}$-welding and $\gamma_{+}$-welding respectively. $\square$