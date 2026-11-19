
> [!definition] Hausdorff Measure
> Suppose $F\subseteq \R^{n}$ and $s>0$. Then for all $\delta>0$, we define $$\mathcal{H}_{\delta}^{s}(F):=\inf\left\{\sum_{i=1}^\infty|U_i|^s:\{U_i\}\text{ is a }\delta\text{-cover of }F\right\},$$where $|U_{i}|$ is the diameter. Then the $s$-dimensional Hausdorff measure is defined as $$\mathcal{H}^{s}(F):=\lim_{\delta\to 0}\mathcal{H}^{s}_{\delta}(F)$$

> [!remark]
> As $\delta$ decreases, the class of permissible covers of $F$ in is reduced. Therefore, the infimum $\mathcal{H}_{\delta}^{s}(F)$ increases, or at least does not decrease. So this limit exists for any subset $F$ of $\R^{n}$, although the limiting value can be (and usually is) $0$ or $\infty$.

> [!proposition]
> The Hausdorff measure is a measure on $\R^{n}$.
> 

> [!definition] Hausdorff Dimension
> Roughly speaking, the Hausdorff dimension of a set $F\subset\R^d$ is the value of $s$ at which the $s$-dimensional Hausdorff measure ‘jump’ from $\infty$ to $0$ occurs. Formally, we define the Hausdorff dimension of $F$ as $$\dim_H F:=\inf\{s\geq 0:\mathcal{H}^{s}(F)=0\}=\sup\{s\geq 0:\mathcal{H}^{s}(F)=\infty\}.$$

> [!corollary] 
> - If $f\colon F \to \mathbb{R}^m$ is a Lipschitz transformation, then  
> $$\dim_H f(F) \leq \dim_H F.$$
> - If $f\colon F \to \mathbb{R}^m$ is a bi-Lipschitz transformation, i.e.,
> $$ c_1 |x - y| \leq |f(x) - f(y)| \leq c_2 |x - y| \quad \text{for } x, y \in F, $$
> where $0 < c_1 \leq c_2 < \infty$, then $$\dim_H f(F) = \dim_H F.$$
> 
> $\quad$

