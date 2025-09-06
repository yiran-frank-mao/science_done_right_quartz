## Transpose



## Determinant

> [!definition] Determinant
> The determinant of a square matrix $A$ is 
> $$ \newcommand{\sgn}{\mathrm{sgn}}\det A:= \sum_{\sigma \in S_{n}} \sgn(\sigma) \prod^{n}_{k=1} A_{k,\sigma(k)}, $$
> where $S_{n}$ is [[Symmetric Group#^5b562f|symmetric group]], $\sigma$ is a [[Symmetric Group#^caba60|permutation]], $\sgn(\sigma)$ is the [[Symmetric Group#^8ed9de|sign of the permutation]], and $A_{k,\sigma(k)}$ denotes the $(k,\sigma(k))$ entry of $A$.
> 

> [!proposition] Cofactor Expansion
> For any $i$, $\det A=\sum_{j=1}^{n} A_{ij} C_{ij}$, where $C_{ij}=(-1)^{i+j} \det (A_{\hat{i}\hat{j}})$, and $A_{\hat{i}\hat{j}}$ denotes the matrix obtained from $A$ by removing the $i$th row and $j$th column.

<u><b>e.g.</b></u>  For a $3\times 3$ matrix $A=\begin{pmatrix}a&b&c\\d&e&f\\g&h&i\end{pmatrix}$, the determinant can be recursively computed as follows: $$\begin{aligned}\det A  &=a\det\begin{pmatrix}e&f\\ h&i\end{pmatrix}-b\det\begin{pmatrix}d&f\\ g&i\end{pmatrix} +c\det\begin{pmatrix}d&e\\ g&h\end{pmatrix}  \\ &=a(ei-fh)-b(di-fg)+c(dh-eg)\end{aligned}$$

> [!proposition]
> Determinant satisfies the following properties:
> - $\det I=1$.
> - If $B$ is obtained from $A$ by scaling a single row by a factor $\alpha\in\R$, then $\det B = \alpha\cdot \det A$. In particular, $\det \alpha A=\alpha^{n}\det A$.
> - If all rows of $A$, $B$, $C$ except the $i$th are same, and for any $j$, $C_{ij}=A_{ij}+B_{ij}$, then $\det C= \det A+ \det B$.
> - If $B$ is obtained by swapping 2 rows of $A$, then $\det B = −\det A$.
> - If $B$ is obtained by adding $\alpha\cdot A_{i}$ to $A_{j}$ for $i\neq j$, then $\det B=\det A$. 
> - $\det AB= \det BA = \det A\det B$.
>$\quad$
