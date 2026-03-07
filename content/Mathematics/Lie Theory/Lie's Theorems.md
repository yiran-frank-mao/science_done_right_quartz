## Baker-Campbell-Hausdorff Formula

> [!theorem] Baker-Campbell-Hausdorff Formula
> Suppose $\newcommand{\[}{\left[\!\left[}\newcommand{\]}{\right]\!\right]}$
> Specially, in the Lie algebra case, we have $$e^{X}e^{Y}=e^{X+Y+[X,Y]/2+[X,[X,Y]]/12+\cdots}$$

> [!corollary]
> Suppose $X,Y\in\g$, then $$e^{X}Ye^{-X}=Y + [X,Y] + \frac{1}{2}[X,[X,Y]] + \cdots =\sum_{n\in \N} \frac{1}{n!} [\overbrace{A,[A, \dots [A}^{n\text{ } A\text{'s}} ,B]\dots]]. $$
> 

*Proof*  This is a consequence 


## Lie's Theorems

> [!theorem] Ado's Theorem
> Every finite‑dimensional Lie algebra admits a faithful finite‑dimensional representation, so it embeds as a Lie subalgebra of matrices $\gl(V)$ for some finite‑dimensional vector space $V$.
> 

> [!theorem] Lie's First Theorem
> If two Lie groups are isomorphic, then so their Lie algebras.

> [!theorem] Lie's Second Theorem
> If $\newcommand{\Lie}{\mathrm{Lie}}\Lie(G)\cong \Lie(H)$, then $G$ and $H$ are locally isomorphic.

 > [!theorem] Lie's Third Theorem
 > For every finite dimensional Lie algebra $\newcommand{\g}{\mathfrak{g}}\g$ there exists a unique simply connected Lie group $G$ with $\Lie(G )=𝔤$. If $G$ is simply connected then $$\newcommand{\Hom}{\mathrm{Hom}}\Hom_{\mathrm{LieGrp}}(G,H)\cong \Hom_{\mathrm{LieAlg}}(\Lie(G),\Lie(H)).$$
> 

## The Adjoint Maps

> [!definition] Adjoint Map of a Lie Group
> The adjoint map of a Lie group $G$ is the map $\newcommand{\Aut}{\mathrm{Aut}}\newcommand{\Ad}{\mathrm{Ad}}\Ad\colon G\to \GL(\Lie(G))$ defined by $$\Ad(g)=\d_{e}(C_g),$$ where $C_g(h)=ghg^{-1}$ is the conjugation by $g$. It turns out to be a group representation called the *adjoint representation* of $G$.
 
> [!proposition]
> For matrix Lie groups, the adjoint map reduces to $\Ad_{g}(X)=gXg^{-1}$ for $g\in G$ and $X\in \Lie(G)$.
> 

> [!proposition]
> Suppose $\varphi\colon G\to H$ is a Lie group homomorphism, then the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/adjoint_map_property_1.svg" alt="https://q.uiver.app/#q=WzAsNCxbMCwwLCJcXG1hdGhmcmFre2d9Il0sWzIsMCwiXFxtYXRoZnJha3tnfSJdLFswLDIsIlxcbWF0aGZyYWt7aH0iXSxbMiwyLCJcXG1hdGhmcmFre2h9Il0sWzAsMSwiXFxtYXRocm17QWR9X2ciXSxbMiwzLCJcXG1hdGhybXtBZH1fe1xcdmFycGhpKGcpfSJdLFswLDIsIlxcbWF0aHJte2R9X2VcXHZhcnBoaSJdLFsxLDMsIlxcbWF0aHJte2R9X2UgXFx2YXJwaGkiXV0=" style="width:25%;"/>
> 

> [!definition] Adjoint Map of a Lie Algebra
> For a [[Lie Algebra#^5007ba|Lie algebra]] $\newcommand{\g}{\mathfrak{g}}\g$ and an element $x \in \g$, the *adjoint map* of $x$ is the linear transformation $\newcommand{\ad}{\mathrm{ad}}\ad_x\colon \g \to \g$ defined by:
> $$ \ad_x(y) = [x, y]. $$
>

> [!proposition] The Adjoint Representation
> The adjoint map $\ad\colon \g \to \mathfrak{gl}(\g)$ is a Lie algebra homomorphism. So the map $\ad\colon \g \to \mathfrak{gl}(\g)$ given by $x \mapsto \ad_x$ is a [[Lie Algebra Representations#^df3ff7|representation]] of $\g$. It is called the *adjoint representation* of $\g$.

*Proof* The Jacobi identity $[x, [y, z]] + [y, [z, x]] + [z, [x, y]] = 0$ can be rewritten as $[x, [y, z]] = [[x, y], z] + [y, [x, z]]$. This is exactly the condition $\ad_x([y, z]) = [\ad_x(y), z] + [y, \ad_x(z)]$, which means $\ad_x$ is a derivation. The homomorphism property $\ad_{[x,y]} = [\ad_x, \ad_y]$ is another consequence of the Jacobi identity. $\square$

> [!theorem] Relationship Between Adjoint Maps
> $\ad=\Lie(\Ad)$ for the [[Functoriality and Naturality#^653948|functor]] $\Lie\colon \mathbf{LieGrp}\to\mathbf{LieAlg}$.
> 

