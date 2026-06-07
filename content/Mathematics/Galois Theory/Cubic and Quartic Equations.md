## Cubic Equations

> [!theorem] Galois Theory of Cubic Equations
> Let $K$ be a splitting field of an irreducible cubic polynomial $\newcommand{\Q}{\mathbb{Q}}\newcommand{\Z}{\mathbb{Z}}\newcommand{\Gal}{\operatorname{Gal}}\newcommand{\C}{\mathbb{C}}f$ over a field $F$, let $\Delta$ be the discriminant of $f$, and $G$ be the Galois group of $K\supset F$. Then the following statements hold:
> - If $\Delta$ is a square in $F$, then $[K:F]=3$ and $G$ is the alternating group $A_{3}$.
> - If $\Delta$ is not a square in $F$, then $[K:F]=6$ and $G$ is the symmetric group $S_{3}$.
>$\quad$

*Proof*  Let $f(x)=x^{3}-a_{1}x^{2}+a_{2}x-a_{3}$ be an irreducible cubic polynomial over $F$ with splitting field $K$. In $K$, we have $f(x)=(x-\alpha_{1})(x-\alpha_{2})(x-\alpha_{3})$. Since $\alpha_{1}+\alpha_{2}+\alpha_{3}=a_{1}\in F$, we can conclude that $K=F(\alpha_{1},\alpha_{2})$, and there is a chain of field extensions: $$F\subset F(\alpha_{1})\subset F(\alpha_{1},\alpha_{2})=K.$$Let $L:=F(\alpha_{1})$, then in $L$, the polynomial can be written as $$f(x)=(x-\alpha_{1})q(x),$$for some quadratic polynomial $q(x)$, which factors as $(x-\alpha_{2})(x-\alpha_{3})$ in $K[x]$. There are only two cases: if $q$ is irreducible in $L[x]$, then $[K:F]=[K:L]\cdot[L:F]=6$, otherwise, $L=K$ and $[K:F]=3$.
As $f$ is irreducible over $F$, $G$ acts transitively on the roots $\alpha_{1},\alpha_{2},\alpha_{3}$, so $G$ must be either $S_{3}$ or $A_{3}$. Consider the square root of the discriminant, say $\delta=\sqrt{\Delta}=(\alpha_{1}-\alpha_{2})(\alpha_{1}-\alpha_{3})(\alpha_{2}-\alpha_{3})$. If $\Delta$ is square, $\delta\in F$, it is then fixed by $G$. Note that $\delta$ can only be fixed by even permutations, so $G=A_{3}$, and $[K:F]=3$. Otherwise, if $\Delta$ is not square, $\delta\notin F$, then $G$ must be $S_{3}$, and $[K:F]=6$. $\square$

Indeed, the above statement can be generalized:

> [!theorem]
> Let $K$ be a splitting field over $F$ of an irreducible polynomial $f$ of degree $n$ in $F[x]$, and let $\Delta$ be the discriminant of $f$. Then the Galois group $\Gal(K/F)$ is a subgroup of the alternating group $A_{n}$ if and only if $\Delta$ is a square in $F$.

## Quartic Equations

For quartic equations, we immediately have the following:

> [!corollary]
> Let $G$ be the Galois group of an irreducible quartic polynomial $f\in F[x]$. The discriminant $\Delta$ of $f$ is a square in $F$ if and only if $G$ contains no odd permutation. Therefore, 
> - If $\Delta$ is a square in $F$, then $G$ is either the [[Symmetric Group#^a33b58|alternating group]] $A_{4}$ or the Klein four-group $D_{2}$.
> - Otherwise, $G$ is $S_{4}$, $D_{4}$, or $C_{4}$.
> $\quad$

Lagrange found another useful expression in the roots, one that is special to quartic polynomials:

> [!definition] Resolvent Cubic
> Let $f(x)$ be an irreducible quartic polynomial over $F$. $\alpha_{1},\alpha_{2},\alpha_{3},\alpha_{4}$ are four roots of $f$. Define $$\beta_{1}:=\alpha_{1}\alpha_{2}+\alpha_{3}\alpha_{4},\quad \beta_{2}:=\alpha_{1}\alpha_{3}+\alpha_{2}\alpha_{4},\quad \beta_{3}=\alpha_{1}\alpha_{4}+\alpha_{2}\alpha_{3},$$then the polynomial $g(x)=(x-\beta_{1})(x-\beta_{2})(x-\beta_{3})$ is called the resolvent cubic of $f$.
> 

> [!remark]
> Given a quartic polynomial $f(x)=x^{4}+dx^3+ax^{2}+bx+c$, a more useful expression of the resolvent polynomial is $g(x)=x^{3}+2ax^{2}+(a^{2}-4c)x-b^{2}$. Notice that the resolvent polynomial is independent of the cubic coefficient $d$. This is because our construction of $\beta_{1}$, $\beta_{2}$ and $\beta_{3}$ cannot produce $d$.
> 

> [!proposition]
> Let $f(x)$ be an irreducible quartic polynomial over $F$. Then the discriminant of $f$ equals to the discriminant of its solvent polynomial $g$
> 

*Proof*  Note that $\beta_{1}-\beta_{2}=(\alpha_{1}\alpha_{2}+\alpha_{3}\alpha_{4})-(\alpha_{1}\alpha_{3}+\alpha_{2}\alpha_{4})=(\alpha_{1}-\alpha_{4})(\alpha_{2}-\alpha_{3})$, so by symmetry, the discriminant of the solvent polynomial $(\beta_{1}-\beta_{2})(\beta_{1}-\beta_{3})(\beta_{2}-\beta_{3})$ is exactly the discriminant of $f$. $\square$

> [!proposition]
> Let $G$ be the Galois group of an irreducible quartic polynomial $f$ over $F$, and let $g$ be the resolvent cubic of $f$. Then $g$ is irreducible if and only if the [[Groups, Order and Subgroups#^3bce31|order]] of $G$ is divisible by $3$. Specifically,
> - If $g$ splits completely in $F$, then $G=D_{2}$.
> - If $g$ has one root in $F$, then $G=D_{4}$ or $C_{4}$.
> - If $g$ is irreducible, then $G=S_{4}$ or $A_{4}$.
> $\quad$

*Proof*  First note that the three elements $\beta_{1}$, $\beta_{2}$ and $\beta_{3}$ are distinct. In fact, since $f$ is irreducible quartic polynomial, its four roots cannot be multiple roots (otherwise the it shares a root with its derivative, contradicting the irreducibility). Thus $$\beta_{1}-\beta_{2}=(\alpha_{1}\alpha_{2}+\alpha_{3}\alpha_{4})-(\alpha_{1}\alpha_{3}+\alpha_{2}\alpha_{4})=(\alpha_{1}-\alpha_{4})(\alpha_{2}-\alpha_{3})\neq 0, $$and similarly for $\beta_{1}-\beta_{3}$ and $\beta_{2}-\beta_{3}$. 
Let $B=\{\beta_{1},\beta_{2},\beta_{3}\}$. The operation in $S_{4}$ on the roots of $f$ induces an action on $B$. If $g$ splits completely in $F$, then $B$ is fixed by $G$, so $G=D_{2}=\{(),(12)(34),(13)(24),(14)(23)\}$.
If $g$ has one root in $F$, say $\beta_{1}\in F$. Let $L=F(\beta_{1},\beta_{2},\beta_{3}),$ then $\Gal(L/F)=C_{2}\cong \Z_{2}$ is a normal subgroup of $G$ by [[Fixed Fields and Galois Extensions#^632791|the theorem]]. So $G$ has to be $C_{4}$ or $D_{4}$.
If $g$ is irreducible, then $3\mid |G|$, we can conclude that $G$ is either $S_{4}$ or $A_{4}$. The converse is also true because $g$ can only be irreducible if $G$ is either $S_{4}$ or $A_{4}$, as we've already showed all other cases above. $\square$

To summarize, we can use the following table to classify the Galois group of a quartic polynomial $f$ based on the the resolvent cubic $g$ and the discriminant $\Delta$ of the resolvent cubic:

|                    | $\Delta$ is square | $\Delta$ is not square |     |
| ------------------ | ------------------ | ---------------------- | --- |
| $g$ is reducible   | $G=D_{2}$          | $G=D_{4}$ or $C_{4}$   |     |
| $g$ is irreducible | $G=A_4$            | $G=S_{4}$              |     |
^ab1d81