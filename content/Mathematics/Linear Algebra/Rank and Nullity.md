## Various Subspaces

> [!definition] Row Space, Column Space, Null Space
> Let $A$ be an $m\times n$ matrix over $\newcommand{\R}{\mathbb{R}}\newcommand{\C}{\mathbb{C}}F\in \{\R,\C\}$. 
> The row space of $A$, denoted $\newcommand{\row}{\mathrm{row}}\row(A)$, is the subspace of $F^{n}$ spanned by the row vectors of $A$.
> The column space of $A$, denoted $\newcommand{\col}{\mathrm{col}}\col(A)$, is the subspace of $F^{m}$ spanned by the column vectors of $A$.
> The null space of $A$, denoted $\newcommand{\null}{\mathrm{null}}\null(A)$ or $\ker (A)$, is the subspace of $F^{n}$ consisting of all solutions to the homogeneous equation $Ax=0$.
> 

We immediately have the following characterization of solutions to linear equations:

> [!proposition]
> The equation $Ax=b$ is consistent iff $b\in \col(A)$. 
> If $x_{0}$ is a particular solution to $Ax=b$, then the complete solution set is $x_{0}+\null(A)$.
> 

## Rank

> [!theorem]
> The row space and column space of a matrix have the same dimension (as subspaces of $F^{n}$).
> 

> [!definition] Rank & Nullity
> The rank of a matrix $A$ is the dimension of $\row(A)$ or $\col(A)$.
> The nullity of a matrix $A$ is the dimension of $\null(A)$.


> [!theorem] 
> For an $n\times n$ matrix $A\in M_{n}(F)$, the followings are equivalent:
> 1. $A$ is invertible;
> 2. $Ax = 0$ has only the trivial solution;
> 3. $rref (A) = I$;
> 4. $A$ is a product of elementary matrices;
> 5. $Ax=b$ is consistent for every $b ∈ F^{n}$;
> 6. $Ax=b$ has exactly one solution for every $b ∈ F$;
> 7. $\det (A) ≠ 0$;
> 8. The column vectors of $A$ are linearly independent;
> 9. The row vectors of $A$ are linearly independent;
> 10. The column vectors of $A$ span $F^{n}$;
> 11. The row vectors of $A$ span $F^{n}$;
> 12. The column vectors of $A$ is a basis for $F^{n}$;
> 13. The row vectors of $A$ is a basis for $F^{n}$;
> 14. $rank (A) = n$;
> 15. $nullity (A) = 0$.
> $\quad$
