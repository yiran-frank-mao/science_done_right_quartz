## Supremum and Infimum

>[!definition]
>**Def**  <i><u>Upper Bound</u></i> and <i><u>Lower Bound</u></i>
For a set $\require{mhchem}\newcommand{\R}{\mathbb{R}}\newcommand{\N}{\mathbb{N}}S\subseteq \R$, if exists $b\in\R$ such that for all $s\in S$, $s\leq b$, then $b$ is an upper bound for $S$. Similarly, if for all $s\in S$, $s\geq b$, then $b$ is called a lower bound.

>[!definition]
>**Def**  <i><u>Supremum</u></i> and <i><u>Infimum</u></i>
$b$ is called supremum of a set $S$ if $b$ is an upper bound and for all upper bound $u$, $b\leq u$. Similarly, $b$ is infimum of $S$ if it is the greatest upper bound.

>[!lemma]
> **Lemma**
> - $b=\sup(S)$ iff for all $\varepsilon>0$ there exists $x\in S$ such that $b-x<\varepsilon$.
> - $b=\inf(S)$ iff for all $\varepsilon>0$ there exists $x\in S$ such that $x-b<\varepsilon$.
> $\quad$

>[!definition]
>**Def**  <i><u>Maximum</u></i> and <i><u>Minimum</u></i>
Suppose $S\subseteq \R$. If there exists $x\in S$ such that $x$ is supremum of $S$, then $x$ is called the maximum of $S$. Similarly, $x$ is called the minimum if $x$ is the infimum lying in $S$.

## Partition and Refinement

>[!definition]
>**Def**  <i><u>Partition of Interval</u></i>
Given interval $[a,b]\subset\R$, a set $P$ is a partition of $[a,b]$ if
>- $P\subseteq[a,b]$.
>- $P$ is finite.
>- $a\in P$ and $b\in P$.
> 
By convention, label the elements in $P$ as: $$a=x_{0}<x_{1}<\dots<x_{n}=b$$

>[!definition]
>**Def**  <i><u>Refinement</u></i>
A partition $Q$ is called refinement of $P$ if $P\subseteq Q$.

>[!proposition]
>**Prop**  If $P$ is a partition of $[a,b]$ then $P$ is a refinement of $\{a , b\}$.

>[!proposition]
>**Prop**  Suppose $P$ and $Q$ are partitions of $[a,b]$, then $P\cup Q$ is a refinement of $P$ and $Q$.

## Riemann-Darboux Integrability

>[!definition]
>**Def**  <i><u>Lower Sum</u></i> and <i><u>Upper Sum</u></i>
Suppose $f\colon[a,b] \to \R$ is a bounded function, and elements of partition $P$ on $[a,b]$ be $x_{0},x_{1}\dots x_{n}$. For each $i\in\N$, $1\leq i\leq n$, we define$$m_{i}= \inf\{f(x):x_{i-1}\leq x\leq x_{i}\},\quad M_{i}= \sup\{f(x):x_{i-1}\leq x\leq x_{i}\}$$Then the lower sum $L(f,P)$ and upper sum $U(f,P)$ are defined by $$L(f,P)=\sum_{i=1}^{n}m_{i}(x_{i}-x_{i-1}),\quad U(f,P)=\sum_{i=1}^{n}M_{i}(x_{i}-x_{i-1})$$

>[!proposition] 
>**Prop**  For all $\varepsilon>0$, there is some partition $P$ such that $$U(f,P)-L(f,P)<\varepsilon$$

>[!definition] Riemann-Darboux Integrability
> Suppose $f\colon[a,b] \to \R$ is a bounded function, $f$ is integrable if $$L_{a}^{b}(f)=U_{a}^{b}(f)$$where $L_{a}^{b}(f)=\sup\{L(f,P):P \text{ is a partition over }[a,b]\}$ and $U_{a}^{b}(f)=\inf\{U(f,P):P \text{ is a partition over }[a,b]\}$. And we define the integral of $f$ be $$\int_{a}^{b}f(x)=L_{a}^{b}(f)=U_{a}^{b}(f)$$ ^e15bc4

>[!lemma]
>**Lemma**  Suppose $f\colon[a,b] \to \R$ be bounded function, $P$ and $Q$ are partitions of $[a,b]$. Then,
>- $L(f,P)\leq U(f,p)$.
>- If $Q$ is a refinement of $P$ then $L(f,P) \leq L(f,Q)$ and $U(f,p)\geq U(f,Q)$.
>- $L(f,P)\leq U(f,Q)$.
>
**Proof**  The first proposition arises from $m_{i}\leq M_{i}$. And $L(f,P)\leq L(f,Q)\leq U(f,Q)$ implies the third proposition.

> [!theorem] Fundamental Theorem of Calculus
> Suppose $f\colon[a,b]\to \R$ is a continuous function, then $f$ is integrable and $$\int_{a}^{b}f(x) = F(b)-F(a)$$where $F(x)=\int_{a}^{x}f(t)\d t$. ^433cc4

