---
created: 2024-08-19
updated: 2025-06-18
completed: true
tags:
  - analysis
  - topology
  - homotopy
---
## Homotopy of Paths

Recall the definition of a homotopy:

![[Homotopy Types#^2c10b4]]

Let $\newcommand{\C}{\mathbb{C}}D\subset \C$ be a domain, and $\gamma, \tilde{\gamma}\colon [0,1] \to D$ be two [[Integration and Primitives#^ea7ec8|paths]] in $D$. So a homotopy from $\gamma$ to $\tilde{\gamma}$ is a continuous map $H\colon [0,1]\times [0,1] \to D$ such that $H(t,0)=\gamma(t)$ and $H(t,1)=\tilde{\gamma}(t)$ for all $t\in [0,1]$.

> [!definition] Closed Path Homotopy, Path with Constant Endpoints Homotopy
>Homotopy $H$ is called a CP-homotopy if each $\gamma_{s}:=H(\cdot, s)$ is a closed path. i.e., $H(0,s)=H(1,s)$ for all $s\in [0,1]$.
>$H$ is called a PCE-homotopy if the beginning and end points of the paths $\gamma_{s}=H(\cdot, s)$ are independent of $s$. i.e. $H(0,s)=H(0,0)$ and $H(1,s)=H(1,0)$ for all $s\in[0,1]$. ^fc0803

<u><b>e.g.</b></u>  The paths $t\mapsto r_{1} e^{2\pi i t}$ and $t\mapsto r_{2} e^{2\pi i t}$ are CP-homotopic in $\C\setminus\{0\}$, as $H(t,s)=(sr_{1}+(1-s)r_{2})e^{2\pi i t}$ is a homotopy between them.

> [!lemma]
> Every closed path in $\C \setminus\{0\}$ is CP-homotopic in $\C \setminus\{0\}$ to one of the form $γ_{n} \colon [0,1] →\C \setminus\{0\}$, $γ_{n}(t) = e^{2πint}$ for $n∈\mathbb{Z}$. ^f5f4b6

## The Homotopy Invariance Theorem

> [!lemma]
> Let $K\subset U\subset \C$, with $K$ [[Compactness of Metric Space#^f1fb8b|compact]] and $U$ [[Open and Closed Sets#^e112b1|open]]. Then there exists $\varepsilon>0$ such that for all $z\in K$, $\Delta(z,\varepsilon)\subset U$. ^220c21

*Proof*  Assume the contrary. Then for all $\varepsilon>0$, there is some $z\in K$ such that $\Delta(z,\varepsilon)\not\subset U$. Let $C:=U^{c}$, a closed set. Choose sequence $(z_{n})\subset K$, $(w_{n})\subset C$ such that $|z_{n}-w_{n}|<\frac1n$. Since $K$ is compact, there is a subsequence $(z_{n_{k}})$ converging to some $z_{0}\in K$. Then $w_{n_{k}}\to z_{0}$. Since $C$ is closed, $z_{0}\in C$, thus $z_{0}\in U^{c}\cap K$, contradicting $K\subset U$. $\square$

> [!theorem] Homotopy Invariance Theorem
> Suppose $f\in H(D)$ for some domain $D$, $\gamma$ and $\tilde{\gamma}$ are two piecewise $C^{1}$ paths in $D$. Let $\Gamma$ be a homotopy from $\gamma$ to $\tilde{\gamma}$. Let $\gamma^{0}=\Gamma(0,\cdot)$ and $\gamma^{1}=\Gamma(1,\cdot)$ be the paths followed by the initial and final points of the homotopy respectively. Then $$\newcommand{\dd}{\:\mathrm{d}}\int_{\gamma}f(z) \dd z + \int_{\gamma^{1}} f(z) \dd z = \int_{\gamma^{0}} f(z)\dd z + \int_{\tilde{\gamma}} f(z) \dd z$$ ^16dbd8

*Proof*  The required equation is equivalent to $$\int_\gamma f(z)\dd{z}+\int_{\gamma^{1}}f(z)\dd{z}-\int_{\gamma^{0}}f(z)\dd{z}-\int_{\tilde{\gamma}}f(z)\dd{z}=0$$This is equivalent to say that showing that the integral around the outside of the “rectangle” is zero. 
![homotopy_invariance_theorem.svg|330](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/homotopy_invariance_theorem.svg)
We will chop it into $N\times N$ pieces of small rectangles. We write $S_{ij}$ for the inner small "rectangle" whose bottom left corner is $\Gamma(i/N, j/N)$, and write $S$ for $\Gamma([0,1]\times[0,1])$. Thus we have $$\int_{\partial S} =\sum_{i,j} \int_{\partial S_{ij}}$$So it suffices to argue that each of these integrals is zero.
We now formalize the above setting, define a family of paths $[0,1]\to D$ by $$\beta_{(i,j)\to(i+1,j)}(t):=\Gamma((i+t)/N,j/N),\quad \beta_{(i,j)\to (i,j+1)}(t):=\Gamma(i/N, (j+t)/N)$$Furthermore, let $$\partial S_{ij}=\left[\beta_{(i,j)\to(i+1,j)};\beta_{(i+1,j)\to(i+1,j+1)};\beta_{(i,j+1)\to(i+1,j+1)}^-;\beta_{(i,j)\to(i,j+1)}^-\right]$$And $\partial S = \left[\gamma;\gamma^{1};\tilde{\gamma}^{-};\gamma^{0-}\right]$. 
Since $S$ is the image of a compact set under a continuous map, $S$ is also compact (see [[Continuity on Metric Space#^3a05b1|theorem]]). Applying the previous [[The Homotopy Invariance Theorem#^220c21|lemma]], there exists $\varepsilon>0$, such that for all $z\in S$, $\Delta(z,\varepsilon)\subset D$. Since $[0,1]\times[0,1]$ is compact, by [[Continuity on Metric Space#^d7d908|theorem]], $\Gamma$ is uniformly continuous, so there is $\delta>0$ such that when $|s-s'|<\delta$ and $|t-t'|<\delta$ we have $|\Gamma(s,t)-\Gamma(s',t')|<\varepsilon$.
Now we choose $N$ such that $1/N<\delta$. Then all $\Gamma(s,t)\in \partial S_{ij}$ satisfy $$|s-i/N|<1/N<\delta,\quad |t-j/N|<1/N<\delta$$Therefore $|\Gamma(s,t)-\Gamma(i/N,j/N)|<\varepsilon$, hence $\partial S_{ij} \subset \Delta(\Gamma(i/N,i/N))$. So by [[Integration and Primitives#^b63dd7|local existence of primitives]], the closed path integral  $\int_{\partial S_{ij}}f(z) \dd z=0$, and the result follows. $\square$

> [!corollary]
> Suppose $f\in H(D)$ for some domain $D$. If $\gamma$ and $\tilde{\gamma}$ are CP-homotopic or PCE-homotopic, then $$\int_\gamma f(z)\dd z=\int_{\tilde{\gamma}}f(z)\dd z$$ ^bc41a1

*Proof*  If $\gamma$ and $\tilde{\gamma}$ are CP-homotopic, then $\gamma^{0}=\gamma^{1}$, and we get the required result. If they are PCE-homotopic, then $\gamma^{0}$ and $\gamma^{1}$ are constant, implying $\int_{\gamma^{0}}f(z)\dd z=\int_{\gamma^{1}}f(z)\dd z=0$. $\square$

<u><b>e.g.</b></u>  $t\mapsto 3+e^{2\pi i t}$ and $t\mapsto e^{2\pi i t}$ are not CP-homotopic in $\C\setminus\{0\}$. We can justify this by observing that $\int_{t\mapsto 3+e^{2\pi i t}}\frac1z\dd z=0$ while $\int_{t\mapsto e^{2\pi i t}}\frac1z\dd z=0$.

## Simply Connected Domains

> [!definition] Simply Connected Domain
> A domain is called simply connected if every closed path in $D$ is CP-homotopic to a constant path. ^708d4a

> [!theorem] Simply Connected Domain Characterisation
> For a domain $D\subset \C$, the following are equivalent:
> - $D$ is [[The Fundamental Group#^3b18ee|simply connected]].
> - $\hat{\C}\setminus D$ is [[Connectedness and Paths#^946cc4|connected]].
> - $\partial D$ in $\hat{C}$ is [[Connectedness and Paths#^946cc4|connected]].
>
> Moreover, if $D$ is bounded, then these are also equivalent to
> - $\C\setminus D$ is [[Connectedness and Paths#^946cc4|connected]].
> - $\partial D$ is [[Connectedness and Paths#^946cc4|connected]].
> $\quad$

<u><b>e.g.</b></u>  $\C\setminus\{0\}$ is not [[The Fundamental Group#^3b18ee|simply connected]] since $\hat{\C}\setminus(\C\setminus\{0\})=\{0,\infty\}$ is not connected.

> [!proposition]
> If $D$ is simply connected and $f\in H(D)$, then for every closed $\gamma\in D$ we have $$\int_{\gamma} f(z) \dd z=0$$

*Proof*  Since on a simply connected domain, every $\gamma$ is CP-homotopic to a constant path $\gamma_{\mathrm{const}}$, then $\int_{\gamma} f(z) \dd z=\int_{\gamma_{\mathrm{const}}} f(z) \dd z=0$. $\square$

> [!corollary]
> If $D$ is simply connected and $f\in H(D)$, then $f$ has a primitive.

*Proof*  Directly from the [[Integration and Primitives#^0e998c|theorem]]. $\square$

> [!proposition]
> Continuous maps preserves simple connectedness.