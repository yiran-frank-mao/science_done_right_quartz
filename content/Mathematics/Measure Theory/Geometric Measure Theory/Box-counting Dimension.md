> [!proposition]
> Let $F\subset\R^{n}$ be any non-empty bounded subset. The following quantities are same:
> - the smallest number of sets of diameter at most $\delta$ that cover $F$;
> - the smallest number of closed balls of radius $\delta$ that cover $F$;
> - the smallest number of cubes of side length $\delta$ that cover $F$;
> - the number of $\delta$-mesh cubes that intersect $F$;
> - the largest number of disjoint balls of radius $\delta$ with centres in $F$.
>
> We shall denote this number by $N_{\delta}(F)$.

> [!definition] Box-counting Dimension
> Let $F\subset\R^{n}$ be any non-empty bounded subset, then we define lower and upper box-counting dimension of $F$ as $$\begin{aligned}\underline{\dim_{B}} F: &= \liminf_{\delta\to 0} \frac{\log N_{\delta}(F)}{-\log \delta}\\ \overline{\dim_{B}} F: &= \limsup_{\delta\to 0} \frac{\log N_{\delta}(F)}{-\log \delta}\end{aligned}$$
> If they are equal, we call it the box-counting dimension of $F$ and denote it by $\dim_{B} F$.

<u><b>e.g.</b></u>  Consider the compact set $F=\left\{0,1,\frac{1}{2},\frac{1}{3},\cdots \right\}$, it has box-counting dimension $\frac12$. Let $0<\delta<\frac{1}{2}$ and let $k$ be the integer satisfying 

## Properties and Problems of Box-counting Dimension

