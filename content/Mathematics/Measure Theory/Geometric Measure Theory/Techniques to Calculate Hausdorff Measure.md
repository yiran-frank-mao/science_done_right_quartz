
> [!definition] Mass Distribution
> A [[Measurable Spaces and Functions#^c2e020|measure]] on a bounded subset of $\R^{n}$ for which $0 < μ(\R^{n}) < \infty$ will be called a mass distribution.

> [!theorem] Mass Distribution Principle
> Let $\mu$ be a mass distribution on $F\subset \R^{n}$, and suppose for some $s>0$, there are numbers $c>0$ and $\varepsilon>0$ such that $$\mu(U)\leq c |U|^{s}$$for all sets $U$ with $|U|\leq\varepsilon$. Then $\newcommand{\H}{\mathcal{H}}\H^{s}(F) \geq\mu(F)/ c$ and $s\leq\mathrm{dim}_\mathrm{H}F\leq\underline{\dim}_\mathrm{B}F\leq\overline{\dim}_\mathrm{B}F.$

*Proof*  Suppose $\{U_{i}\}_{i=1}^{\infty}$ is a [[Compactness of Topological Space#^eb1952|cover]] for $F$, $F\subset \cup_{i}^{\infty}U_{i}$, then $$0<\mu(F)\leq \mu(\cup_{i}^{\infty}U_{i})\leq \sum_{i=1}^{\infty}\mu(U_{i})\leq c\sum_{i} |U_{i}|^{s}.$$Taking infimum, we have $\H^{s}_{\delta}(F)\geq \mu(F)/c$ for sufficiently small $\delta$. Thus, $\H^{s}(F)\geq \mu(F)/c$. In particular, since $\mu(F)>0$, we get $\dim_{\mathrm{H}}F\geq s$. $\square$

## Potential Theoretic Methods

> [!definition] $s$-Potential
> For some $s\geq 0$, the $s$-potential at a point $x\in\R^{n}$, resulting from the mass distribution $\mu$ on $\R^{n}$ is defined as $$\phi_{s}(x):=\int \frac{1}{|x-y|^{s}}\dd\mu(y).$$

> [!remark]+ This is a Generalization of The Gravitational Potential
> If we are working in $\R^3$ and $s = 1$, then this is essentially the familiar Newtonian gravitational potential.

> [!definition] $s$-Energy
> The $s$-energy of a mass distribution $\mu$ on $\R^{n}$ is defined as $$I_s(\mu):=\int\phi_{s}(x)\dd\mu(x) = \iint \frac{1}{|x-y|^{s}}\dd\mu(x)\dd\mu(y).$$

> [!theorem] 
> Let $F$ be a subset of $\R^n$.
> - If there is a mass distribution $\mu$ on $F$ with $I_s(\mu) < \infty$, then $\H^{s}(F) = \infty$ and $\dim_H F \ge s$.
> - If $F$ is a Borel set with $0 < \H^{s}(F) < \infty$, then for all $0 < t < s$, there exists a mass distribution $\mu$ on $F$ with $I_t(\mu) < \infty$.
>$\quad$

*Proof*  