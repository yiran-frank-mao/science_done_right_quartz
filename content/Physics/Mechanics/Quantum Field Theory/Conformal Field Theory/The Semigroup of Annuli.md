In [[The Integrability Theorem|the integrability theorem]], we demonstrated that every projective representation of $\mathfrak{X}_{\C}(S^{1})$ integrates to a projective representation of $\newcommand{\Diff}{\mathrm{Diff}}\Diff^+(S^1)$, and so does $\mathfrak{X}_{\R}(S^{1})$. This result initially appears paradoxical, as one might expect a real Lie algebra to integrate to a real Lie group, with its complexification integrating to the complexification of that group. However, this expectation is not met here, as $\Diff^{+}(S^1)$ lacks a complexification. Instead, an "almost" complexification of it is a semigroup of annuli.

## $\Diff^+(S^1)$ Cannot be Complexified

> [!theorem]
> $\Diff^+(S^1)$ does not admit a complexification.
> 

*Proof*  We can see this by contradiction. If there were a complex Lie group $G$ serving as the complexification, then 

## The Semigroup of Annuli

> [!definition] Semigroup of Annuli
> The *semigroup of annuli*, denoted $\newcommand{\Ann}{\mathrm{Ann}}\Ann$, consists of equivalence classes of triples $\newcommand{\phiin}{\gamma_{\text{in}}}\newcommand{\phiout}{\gamma_{\text{out}}}(\Sigma, \phiin, \phiout)$ where $\Sigma$ is a Riemann surface biholomorphic to an annulus, and $\phiin\colon S^{1}\to \partial_{\text{in}} \Sigma$, $\phiout\colon S^{1}\to \partial_{\text{out}} \Sigma$ are parametrizations of the inner and outer boundary components of $\Sigma$, respectively. Both $\phiin$ and $\phiout$ are orientation-preserving smooth diffeomorphisms onto their images.
> Two annuli $(\Sigma, \phiin, \phiout)$ and $(\Sigma', \phiin', \phiout')$ are considered equivalent if there exists a biholomorphic map $f\colon \Sigma\to \Sigma'$ such that $f\circ \phiin = \phiin'$ and $f\circ \phiout = \phiout'$.
> The semigroup operation is defined by sewing annuli along their boundaries. Given two annuli $(\Sigma, \phiin, \phiout)$ and $(\Sigma', \phiin', \phiout')$, their product is obtained by identifying the outer boundary of $\Sigma$ with the inner boundary of $\Sigma'$ via the parametrizations $\phiout$ and $\phiin'$. The resulting annulus is $(\Sigma\sqcup \Sigma' / \phiin'(e^{i\theta})\sim\phiout(e^{i\theta}), \phiin,\phiout')$, and we shall simply denote it by $\Sigma\cdot \Sigma'$.
> 

> [!remark]+
> What we really care about here is not the plain annuli, but the rigged annuli that including the parametrisation information of the boundaries (riggings). If you forget the boundary parametrisations and look only at conformal isomorphism classes of annuli, then every annulus is conformally equivalent to a round annulus $\Sigma_{r}​=\{r<∣z∣<1\}$ $(0<r<1)$, and its conformal type is determined by a single real number $r$. 
> In other words, every annulus is simply a tuple of two smoothly parameterized Jordan curves $(\phiin,\phiout)$ such that $\newcommand{\Int}{\mathrm{Int}}\Int(\phiin)\subset \Int(\phiout)$ and $\phiin(S^{1})\cap\phiout(S^{1})=\emptyset$.

Clearly, the welding of two annuli remains an annulus topologically, we need to verify that the resulting annulus can be given a complex structure. This is discussed in [[Conformal Welding Problem|conformal welding problem]].
An algebraic description of elements in $\Ann$ is via formal products of maps. For any element in $\Ann$, we can pick a standard representative, i.e., a round annulus $(\Sigma_{e^{-t}}, \phiin,\phiout)​$ $(t>0)$, and represent it by a formal product $$\phiin \circ \sigma_{t} \circ \phiout^{-1}\colon S^{1}\to S^{1}$$where $\sigma_{t}(z)=e^{-t}z$ is the contraction map. For example, if we have two annuli represented by $r_{\alpha}\sigma_{t}r_{\beta}$ and $r_{\alpha'}\sigma_{s}r_{\beta'}$, then their product is represented by $$\phi_{1}^{-1}\circ \sigma_{t_{1}+t_{2}} \circ \psi_{2}.$$

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