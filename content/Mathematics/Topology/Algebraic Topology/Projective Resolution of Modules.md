---
completed: true
updated: 2025-10-23
created: 2025-10-22
tags:
  - algebraic-topology
  - algebra
  - cohomology
  - homological-algebra
  - functors
---
## The Hom Functor and Projective Modules

The cohomology groups of a space are not independent of its homology groups. The relationship is given by the Universal Coefficient Theorem:

![[Universal Coefficient Theorem#^2162f3]]

The issue here is that given a [[Abelian Categories#^0c5eb9|short exact sequence]] $0 \to A \xrightarrow{i} B \xrightarrow{j} C \to 0$, applying the [[Functoriality#^653948|contravariant  functor]] does not necessarily yield another short exact sequence. For example, consider the short exact sequence $\newcommand{\Z}{\mathbb{Z}} 0 \to \Z \xrightarrow{\times 2} \Z\to \Z/2 \to 0$. Applying the $\newcommand{\Hom}{\operatorname{Hom}}\Hom(-, \Z)$ functor gives the sequence $0 \rightarrow \Hom(\Z/2, \Z) \rightarrow \Hom(\Z, \Z) \xrightarrow{\times 2} \Hom(\Z, \Z)\rightarrow 0$. However, $\Hom(\Z/2, \Z) = 0$, $\Hom(\Z,\Z)\cong \Z$, thus, the sequence is not exact at the second last position. To fix this problem, we will introduce the $\newcommand{\Ext}{\operatorname{Ext}}\Ext$ functor, which measures the failure of exactness when applying the $\Hom$ functor. Before that, we first see when the $\Hom$ functor preserves exactness, which leads us to the notion of projective modules.

> [!definition] Projective Module
> An [$R$-module](Modules#%5E697aa9%7C$R$-module.md) $P$ is *projective* if for any surjective [[Modules#^c11e09|homomorphism]] $f\colon M \to N$ of $R$-modules and any homomorphism $\varphi\colon P \to N$, there exists a lift $\tilde{\varphi}\colon P \to M$ such that $f \circ \tilde{\varphi} = \varphi$.
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/projective_modules.svg" alt="projective_modules" style="width:20%;"/> ^8554fa

<u><b>e.g.</b></u>  [[Modules#^c08671|Free modules]] are projective, because we can choose $y_{i}\in M$ such that $f(y_{i})=\varphi(x_{i})$ for each basis element $x_{i}$ of $P$, and define the lift $\tilde{\varphi}$ on the basis and extend linearly.

> [!lemma]
> The following hold for [$R$-modules](Modules#%5E697aa9%7C$R$-module.md):
> 1. Let $0 \to A \xrightarrow{i} B \xrightarrow{j} C \to 0$ be a short exact sequence of $R$-modules. Then for any $R$-module $G$, the induced sequence $$0 \to \Hom(C, G) \xrightarrow{j^{*}} \Hom(B, G) \xrightarrow{i^{*}} \Hom(A, G)\to 0$$ is exact at $\Hom(C, G)$ and $\Hom(B, G)$.
> 2.  A short exact sequence $0 \to A \to B \to C \to 0$ splits if $C$ is projective.
> 3.  If $0 \to A \to B \to C \to 0$ is a split short exact sequence, then applying the $\Hom(-,G)$ functor results in another split short exact sequence.
> $\quad$

*Proof*  The proof of (1) requires showing exactness at each position.
- **Exactness at $\Hom(C, G)$ (i.e., $j^*$ is injective):** Suppose $j^*(\varphi) = 0$ for some $\varphi \in \Hom(C, G)$. By definition, $j^*(\varphi) = \varphi \circ j$. So, $\varphi \circ j = 0$. Since the original sequence is exact, $j$ is surjective, so $\varphi$ must be the zero map.
- **Exactness at $\Hom(B, G)$:** First, we show $\newcommand{\im}{\operatorname{im}}\im(j^*) \subseteq \ker(i^*)$. Since the original sequence is exact at $B$, the composition $j \circ i$ is the zero map. Therefore, $(j \circ i)^* = 0^* = 0$.
  Next, we show $\ker(i^*) \subseteq \im(j^*)$. Suppose $\psi \in \ker(i^*)$, which means $\psi \in \Hom(B, G)$ and $i^*(\psi) = \psi \circ i = 0$. This implies that $\im(i) \subseteq \ker(\psi)$. Since the original sequence is exact, $\im(i) = \ker(j)$. Thus, $\ker(j) \subseteq \ker(\psi)$. By the first isomorphism theorem, $\psi$ factors through the quotient $B/\ker(j)$. Since $j$ is surjective, we have an isomorphism $B/\ker(j) \cong C$. This gives a well-defined map $\bar{\psi}: C \to G$ such that $\psi = \bar{\psi} \circ j$. By definition, this means $\psi = j^*(\bar{\psi})$, so $\psi \in \im(j^*)$.

Now we prove (2). The following diagram illustrates the situation, so that the splitting lemma can be applied:<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/projective_module_short_exact_sequence.svg" alt="projective_module_short_exact_sequence" style="width:60%;"/>
(3) follows simply from the fact that $\Hom(A\oplus C,G)\cong \Hom(A,G)\cong \Hom(C,G)$.  $\square$

## Projective Resolutions

> [!definition] Projective Resolution and Ext Functor
> A *projective resolution* of a module $M$ is an exact sequence
> $$\dots \to P_2 \to P_1 \to P_0 \to M \to 0$$
> where each $P_i$ is a [[Projective Resolution of Modules#^8554fa|projective module]]. We denote this by $P_\bullet \to M$.
> Taking a projective resolution of $M$, remove the $M$ term, and apply the functor $\operatorname{Hom}(-,G)$. This yields a cochain complex:
> $$0 \to \operatorname{Hom}(P_0, G) \to \operatorname{Hom}(P_1, G) \to \operatorname{Hom}(P_2, G) \to \dots$$
> The cohomology of this complex is denoted $H^{*}(\Hom(P_\bullet, G))$. $\Ext_{R}^n(M,G)$ is defined as the $n$-th cohomology  group $H^n(\Hom(P_\bullet, G))$. ^4c2101

However, this is not well-defined so far. We need to check that different projective resolutions of $M$ yield isomorphic $\Ext$ groups.

> [!theorem] Fundamental Theorem of Homological Algebra
> Let $f\colon M \to N$ be a homomorphism of $R$-modules. Let $(P_\bullet, d)$ and $(Q_\bullet, e)$ be [[Projective Resolution of Modules#^4c2101|projective resolutions]] of $M$ and $N$ respectively. Then:
> 1.  There exists a chain map $f_{\bullet}\colon P_{\bullet} \to Q_{\bullet}$ that extends $f$, meaning $f_{n} \circ d = e \circ f_{n+1}$.
> 2.  Any two such chain maps $f_{\bullet}$ and $f_{\bullet}'$ that extend $f$ are chain homotopic.
> $\quad$

*Proof*  The proof is constructive and proceeds by induction on the degree $n$.
* **Base Case**: By projectivity of $P_0$, we can lift the map $f \circ d_{0}\colon P_0 \to N$ to a map $f_{0}\colon P_0 \to Q_0$ such that $e \circ \alpha_0 = f \circ d_{0}$:
  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/fundamental_theorem_of_homological_algebra.svg" alt="https://q.uiver.app/#q=WzAsNCxbMCwyLCJRXzAiXSxbMiwyLCJOIl0sWzIsMSwiTSJdLFsyLDAsIlBfMCJdLFswLDEsImVfMCIsMCx7InN0eWxlIjp7ImhlYWQiOnsibmFtZSI6ImVwaSJ9fX1dLFsyLDEsImYiXSxbMywyLCJkXzAiXSxbMywwLCJmXzAiLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XV0=" style="width:20%;"/>
* **Inductive Step:** Assuming $f_0, \dots, f_{n-1}$ have been constructed to form a chain map up to that degree, we construct $f_{n}\colon P_n \to Q_n$ as follows:
  <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/fundamental_theorem_of_homological_algebra_2.svg" alt="https://q.uiver.app/#q=WzAsOCxbMiwwLCJQX24iXSxbMiwxLCJcXG9wZXJhdG9ybmFtZXtpbX1kX24iXSxbMiwyLCJcXGtlciBlX3tuLTF9Il0sWzAsMiwiUV9uIl0sWzQsMCwiUF97bi0xfSJdLFs0LDIsIlFfe24tMX0iXSxbNiwyLCJRX3tuLTJ9Il0sWzYsMCwiUF97bi0yfSJdLFswLDEsImRfbiJdLFsxLDIsImZfe24tMX0iXSxbMCwzLCJmX24iLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMywyLCJlX24iLDIseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJlcGkifX19XSxbNCw1LCJmX3tuLTF9Il0sWzUsNiwiZV97bi0xfSJdLFs0LDcsImRfe24tMX0iXSxbNyw2LCJmX3tuLTJ9IiwyXV0=" style="width:60%;"/>
  Since the RHS diagram commutes, we can conclude that $f_{n-1}(\im d_{n})\subseteq \ker e_{n-1}=\im e_{n}$. So the projectivity implies the LHS diagram commutes, completing the inductive step.

Now suppose both $f_{\bullet}$ and $f_{\bullet}'$ are chain maps extending $f$. We show they are chain homotopic by constructing homotopy maps $h_{n}\colon P_n \to Q_{n+1}$ inductively:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/fundamental_theorem_of_homological_algebra_3_uniqueness.svg" alt="https://q.uiver.app/#q=WzAsMyxbMiwwLCJQX24iXSxbMCwyLCJRX3tuKzF9Il0sWzIsMiwiXFxvcGVyYXRvcm5hbWV7aW19IGVfe24rMX0iXSxbMCwxLCJoX24iLDIseyJzdHlsZSI6eyJib2R5Ijp7Im5hbWUiOiJkYXNoZWQifX19XSxbMSwyLCJlX3tuKzF9IiwyXSxbMCwyLCJmX24gLWZfbicgLWhfe24tMX1cXGNpcmMgZF9uICJdXQ==" style="width:34%;"/> $\square$

> [!corollary]
> Let $P_\bullet$ and $Q_\bullet$ be two [[Projective Resolution of Modules#^4c2101|projective resolutions]] of the same module $M$. Then there is a chain homotopy equivalence between them. Consequently, for any module $G$,
> $$H^n(\Hom(P_\bullet, G)) \cong H^n(\Hom(Q_\bullet, G))$$

*Proof*  By the above theorem, we can find chain maps $f_{\bullet}\colon P_\bullet \to Q_\bullet$ and $g_{\bullet}: Q_\bullet \to P_\bullet$, both extending the identity on $M$:
<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/fundamental_theorem_of_homological_algebra_corollary.svg" alt="fundamental_theorem_of_homological_algebra_corollary" style="width:20%;"/>
The composition $g_{\bullet} \circ f_{\bullet}\colon P_\bullet \to P_\bullet$ is a chain map extending $\operatorname{id}_M$, must be chain homotopic to $\operatorname{id}_{P_\bullet}$. Similarly, $f_{\bullet} \circ g_{\bullet}$ is chain homotopic to $\operatorname{id}_{Q_\bullet}$. Chain homotopic maps induce the same map on cohomology. Therefore, the induced maps on cohomology, $f^*$ and $g^*$, are inverses of each other, establishing an isomorphism. $\square$

## The Ext Functor

The previous result shows that the cohomology groups $H^n(\Hom(P_\bullet, G))$ depend only on the modules $M$ and $G$, not on the specific projective resolution $P_\bullet$ chosen for $M$. This allows us to make a well-defined definition of the Ext functor: $$\Ext^{n}_{R}(M, G) := H^n(\Hom(P_\bullet, G)).$$

> [!proposition]
> We have the following properties of the Ext functor:
> 1. $\Ext^{0}_{R}(M, G) \cong \Hom_{R}(M, G)$.
> 2. $\Ext^{n}_{\Z}(M, G) \cong 0$ for $n>1$.
> $\quad$

> [!remark]+ Classification of Extensions
> The Ext functor gets its name from its connection to extensions of modules. For $n=1$, the group $\Ext^1_R(M, G)$ provides a classification of the collection of all short exact sequences of the form
> $$0 \to G \to E \to M \to 0$$
> up to a natural equivalence. These sequences are called "extensions" of $M$ by $G$. For the ring of integers $\mathbb{Z}$, it is common to abbreviate $\Ext^1_{\mathbb{Z}}$ to simply $\Ext$.