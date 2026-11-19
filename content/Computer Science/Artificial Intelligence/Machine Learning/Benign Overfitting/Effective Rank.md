**Def**  <i><u>Effective Rank</u></i>
The effective rank of a matrix $A\in\R^{n\times n}$ with eigenvalues $\lambda_{1},\lambda_{2},\dots,\lambda_{m}$ in descending order is defined as:$$r_{k}(A)=\frac{\sum_{i>k}\lambda_{i}}{\lambda_{k+1}}$$**Prop**  For all matrix $A\in\R^{n\times n}$, $r_{k}(A)\geq1$.
**Proof**  $$r_{k}(A)=\frac{\sum_{i>k}\lambda_{i}}{\lambda_{k+1}}\geq\frac{\lambda_{k+1}}{\lambda_{k+1}}=1$$

**Thrm**  Suppose $A\in\R^{n\times n}$, then$$\lambda_{k}=\lambda_{1}(r_{0}(A)-1)r_{k-1}(A)^{-1}\prod_{j=1}^{k-2}(1-r_{j}^{-1})$$**Proof**  Since $r_{k}(A)=\frac{\sum_{i>k}\lambda_{k}}{\lambda_{k+1}}$,$$\lambda_{k+1}r_{k}(A)=\sum_{i>k}\lambda_{k} \implies \lambda_{k+1}(r_{k}(A)-1)=\sum_{i>k+1}\lambda_{i}$$Thus $\lambda_{k}(r_{k-1}(A)-1)=\sum_{i>k}\lambda_{i}$. Subtract the above two equations,$$\lambda_{k+1}(r_{k}(A)-1)-\lambda_{k}(r_{k-1}(A)-1)=-\lambda_{k+1}$$It implies $\frac{\lambda_{k+1}}{\lambda_{k}}=\frac{r_{k-1}(A)-1}{r_{k}(A)}$. Hence we have$$\begin{aligned}
\lambda_{k}&=\frac{\lambda_{k}}{\lambda_{k-1}}\cdot\frac{\lambda_{k}}{\lambda_{k-1}}\dots\frac{\lambda_{2}}{\lambda_{1}}\cdot\lambda_{1}\\
&=\lambda_{1}\cdot\prod_{j=2}^k\frac{r_{j-2}(A)-1}{r_{j-1}(A)}\\
&=\lambda_{1}(r_{0}(A)-1)r_{k-1}(A)^{-1}\prod_{j=1}^{k-2}(1-r_{j}(A)^{-1})
\end{aligned}$$