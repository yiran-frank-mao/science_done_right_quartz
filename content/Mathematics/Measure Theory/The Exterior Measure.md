## Exterior Measure

The notion of exterior measure is the first of two important concepts needed to develop a theory of measure. Loosely speaking, the exterior measure $m_{*}$ assigns to any subset of $\R^{d}$ a first notion of size.

We shall first define the rectangle and cube in $\newcommand{\R}{\mathbb{R}}\R^{n}$.

> [!definition] Rectangle & Cube
> A (closed) rectangle $R$ in $\R^{d}$ is given by the product of $d$ one-dimensional closed and bounded intervals $$R=[a_{1},b_{1}]\times[a_{2},b_{2}]\times\cdots\times [a_{d},b_{d}].$$Moreover, a cube is a rectangle for which $b_{i}-a_{i}=b_{j}-a_{j}$ for all $i,j$.

> [!theorem]
> Every open subset $U$ of $\R^{d}$ with $d\geq 1$ can be written as a [[Equinumerous and Countability#^79eb6c|countable]] union of almost disjoint closed cubes.
> 

> [!definition] Exterior Measure
> If $E$ is any subset of $\R^{d}$, then the exterior (outer) measure of $E$ is a function $m_{*}\colon\mathcal{P}(\R^{d})\to[0,\infty]$ that $$m_{*}(E):= \inf_{\cup_{j=1}^{\infty} Q_{j} \supset E}  \sum_{j=1}^{\infty} |Q_{j}|$$where the infimum is taken over all countable coverings of closed cubes.

> [!proposition]
> Follow from the definition, we immediately have
> - $m_{*}(\emptyset)=m_{*}(\{x\})=0$.
> - The exterior measure of a rectangle is its volume.
> - $m_{*}(\R^{d})=\infty$.
> - $m_{*}$ is translation invariant.
> $\quad$

*Proof*  A single point set can be viewed as a cube of side length zero.

## Properties of Exterior Measure

> [!proposition] Monotonicity
> If $E\subseteq F\subseteq \R^{d}$, then $m_{*}(E)\leq m_{*}(F)$.
> 

*Proof*  Any countable covering of $F$ also covers $E$. $\square$

> [!corollary]
> Any bounded $E\subseteq \R^d$ has finite exterior measure.

*Proof*  If $E$ is bounded, then $E\subseteq [-M,M]^{d}$ for some $M>0$. $\square$

> [!proposition] Countable Subadditivity
> If $E=\cup_{j=1}^{\infty} E_{j}$, then $m_{*}(E)\leq \sum_{j=1}^{\infty} m_{*}(E_{j})$.

*Proof*  For each $E_{j}$, we can find a countable covering of closed cubes $\left\{Q_{k}^{(j)}\right\}_{k}$ such that $\sum_{k=1}^{\infty} |Q_{k}^{(j)}|\leq m_{*}(E_{j})+\frac{\epsilon}{2^{j}}$ as $m_{*}(E)$ is the infimum. Note that $\left\{Q_{k}^{(j)}\right\}_{k,j}$ covers $E$. So we have $$m_{*}(E)\leq \begin{align}\sum_{j=1}^{\infty}\sum_{k=1}^{\infty} |Q_{k}^{(j)}|\leq \sum_{j=1}^{\infty}m_{*}(E_{j})+\sum_{j=1}^{\infty}\frac{\epsilon}{2^{j}}\leq \sum_{j=1}^{\infty}m_{*}(E_{j})+\epsilon\end{align}.$$As this holds for all $\epsilon$, taking the limit $\epsilon\to 0$ gives the desired inequality. $\square$

> [!proposition] Open Sets Approximation
> If $E\subset\R^{d}$, then $m_{*}(E)=\inf_{O\supseteq E} m_{*}(O)$ where $O$ is open.

*Proof*  By monotonicity, it is clear that $m_{*}(E)\leq\inf_{O\supseteq E} m_{*}(O)$. For the other direction, we can find a countable covering of closed cubes $\{Q_{j}\}$ such that $\sum_{j=1}^{\infty} |Q_{j}|\leq m_{*}(E)+\epsilon/2$. Then, we expand each $Q_{j}$ to an open cube $\tilde{Q}_{j}$ containing $Q_{j}$, and such that $|\tilde{Q}_{j}|\leq |Q_{j}| + \epsilon/2^{j+1}$. Then let $O:=\cup_{j=1}^{\infty} \tilde{Q}_{j }$ which is open, and by countable subadditivity, we have $$\inf_{O\supseteq E} m_{*}(O)\leq m_{*}(O)\leq \sum_{j=1}^{\infty} |\tilde{Q}_{j}|\leq \sum_{j=1}^{\infty}\left(|Q_{j}|+\epsilon/2^{j+1}\right)\leq m_{*}(E)+\epsilon/2+\epsilon/2= m_{*}(E)+\epsilon.$$Since $\epsilon$ is arbitrary, we have the desired inequality. $\square$

> [!proposition] 
> The exterior measure is also the infimum size of rectangular coverings:$$m_{*}(E):= \inf_{\cup_{j=1}^{\infty} R_{j} \supset E}  \sum_{j=1}^{\infty} |R_{j}|$$

> [!proposition]
> If $E= E_1\cup E_2$, and $d(E_1,E_2)>0$, then $$m_*(E)=m_*(E_1)+m_*(E_2).$$

> [!remark]
> One _cannot_ conclude in general that if $E_1 \cup E_2$ is a disjoint union of subsets of  $\mathbb{R}^d$, then $$m_*(E_1 \cup E_2) = m_*(E_1) + m_*(E_2).$$In fact it holds when the sets are not highly irregular or “pathological” but are [[Lebesgue Measurability#^b5a209|measurable]].

> [!proposition]
> If a set $E$ is the countable union of almost disjoint cubes $E=\cup_{j=1}^{\infty} Q_{j}$, then $$m_*(E)=\sum_{j=1}^\infty|Q_j|,$$where cubes are almost disjoint if their [[Interior, Exterior and Boundary#^7741a2|interiors]] are disjoint: $Q_{i}^{\circ}\cap Q_{j}^{\circ}=\emptyset$ for all $i\neq j$.