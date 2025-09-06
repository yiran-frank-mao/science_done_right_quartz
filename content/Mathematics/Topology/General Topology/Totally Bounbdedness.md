
>[!definition] 
>**Def**  <i><u>Totally Bounbdedness</u></i>
>A set $A$ in a metric space $(X,d)$ is called totally bounded if for any $δ > 0$ there exist finitely many points $x_1,\dots ,x_{n} ∈ X$ such that $$A\subset\bigcup_{i=1}^{n}B_\delta(x_{i})$$

>[!proposition] 
>**Prop**  Totally bounded sets must be [[Open and Closed Sets#^7012df|bounded]], but bounded sets may not be totally bounded.

>[!proposition] 
>**Prop**  Bounded sets in $\R^{n}$ are totally bounded.
>**Proof**  Let $A$ be a bounded set in $\R^{n}$. Then there is $R > 0$ such that $$A\subset D:=\{(x_1,\cdots,x_n):|x_i|\leq R\mathrm{~for~}i=1,\cdots,b\}$$For any $δ > 0$, we take an integer $N > R\sqrt{n/δ}$ and divide $D$ into $N^{n}$ small cubes of equal size with length $2R/N$. Let $y(ν)$, $ν = 1,\dots ,N^{n}$ denote the center of these cubes. Then for any $x ∈ A$ there is $ν ∈ {1,\dots ,N^{n}}$ such that $|x_{i} −y_{i}(ν)| ≤ R/N$ for all $i = 1,\dots ,n$. Therefore $$\|x-y^{(\nu)}\|^{2}=\sum_{i=1}^n|x_i-y_i^{(\nu)}|^2\leq\frac{nR^2}{N^2}<\delta$$

**Thrm**  A metric space $(X,d)$ is compact iff it is complete and totally bounded.
**Proof**  Assume $(X,d)$ is compact. Let $(x_{n})$ be any Cauchy sequence. Since $X$ is sequentially compact, $(x_{n})$ has a convergent subsequence. According to [[Complete Metric Space#^80b2f4|theorem]], $(x_{n})$ is convergent. Thus $X$ is complete. To see the totally boundedness of $X$ , note that for any $δ > 0$ we have $$X\subset \bigcup_{x\in X}B_\delta(x)$$By the compactness of $X$, we can find $x_{1},\dots ,x_{n} ∈ X$ such that $$X=\bigcup_{i=1}^nB_\delta(x_i)$$Therefore $X$ is totally bounded. Conversely, assume $X$ is complete and totally bounded. We show $X$ is sequentially compact.