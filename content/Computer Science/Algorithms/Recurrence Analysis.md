> [!definition] Recurrence
> A *recurrence* is an equation/inequality according to which the $n$th term of a sequence of numbers is equal to some combination of the previous terms.

There are roughly three methods to solve recurrences:
1. **Substitution Method**: Guessing the closed form using substitution and then prove by induction.
2. **Recursion Tree**: Guessing the closed form using the recurrence tree and then prove by induction.
3. **Master Theorem**: Finding asymptotic bounds of some recurrences using predefined rules.

We will now introduce the last two methods.

## Recursion Tree

> [!definition] Recursion Tree
> *Recursion tree* is a tree where:
> - Each node represents a single sub-problem along with the cost of the particular sub-problem.
> - An edge from node $v$ to node $u$ means that the sub-problem represented by node $v$ calls the sub-problem represented by node $u$.
> $\quad$

<b><u>e.g.</u></b> For the recurrence $T(n)=T(\frac{n}{3})+T(\frac{2n}{3})+cn$ where $c$ is a constant and $T(1)=1$:
![recurrence|450](https://i.imgur.com/3DPRnCE.png)
Note that not all leaves are in the last level, hence the total cost is at most $$\# \text{levels} \times 𝑐𝑛=cn(\log_{\frac{3}{2}}n+1) \in O(n\log n).$$

## Master Theorem

> [!theorem] Master Theorem
> Consider $T(n)=a T(\frac{n}{b})+f(n),\,a\geq1,b>1$, $\frac{n}{b}$ can be $\lceil \frac{n}{b} \rceil$ or $\lfloor \frac{n}{b} \rfloor$.
> 1. If $f(n)=O(n^{(\log_{b}a)-\epsilon})$ for some constant $\epsilon>0$, then $T(n)=\Theta(n^{\mathrm{log}_{b}\,a})$.
> 2. If $f(n)=\Theta(n^{\log_{b}a})$, then $T(n)=\Theta(n^{\log_{b}a}\log n)$. More generally, if $f(n)=\Theta(n^{\log_{b}a}(\log n)^k)$ for some integer $k\geq 0$, then $T(n)=\Theta(n^{\log_{b}a}(\log n)^{k+1})$.
> 3. If $f(n)=\Omega(n^{(\log_{b}\,a)+\epsilon})$ for some constant $\epsilon>0$ and if $a f(\frac{n}{b})\leq c f(n)$ for some constant $c<1$ and $n>n_0$, then $T(n)=\Theta \bigl( f(n) \bigr)$.
> $\quad$

<b><u>e.g.</u></b> Consider $T(n)=2T\left({\frac{n}{2}}\right)+n$. Here $a=2$, $b=2$, $f(n)=n$. Hence $n^{\log_b a}=n$. Therefore by second case of Master theorem we have $T(n)=\Theta(n\log n)$.