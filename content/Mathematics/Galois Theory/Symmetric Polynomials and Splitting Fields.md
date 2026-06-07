> The more symmetric $\alpha$ is, the closer it is to the base field $F$.

> [!theorem] Symmetric Functions Theorem
> Every symmetric polynomial $f(x_{1},x_{2},\dots,x_{n})\in R[x_{1},\dots x_{n}]$ with coefficients in a ring $R$ can be written in a unique way as a polynomial in the elementary symmetric polynomials. ^fc4c03

<u><b>e.g.</b></u>  

> [!corollary]
> Suppose that a polynomial $f(x)=x^{n}+a_{1}x^{n-1}+\dots+ a_{n}$ has coefficients in a [[Ring, Field and Integral Domain#^575174|field]] $F$, and it splits completely in an extension field $K$, with roots $\alpha_{1},\dots,\alpha_{n}$. Let $g(u_{1},\dots ,u_{n})$ be a symmetric polynomial in $u_{1},\dots ,u_{n}$ with coefficients in $F$. Then $g(\alpha_{1},\dots,\alpha_{n})\in F$. 

*Proof*  [[Symmetric Polynomials and Splitting Fields#^fc4c03|Symmetric functions theorem]] tells that $g$ is a polynomial in the elementary symmetric functions. Say that $g(u_{1},\dots,u_{n})=\tilde{g}(s_{1}(u),\dots,s_{n}(u))$, where $\tilde{g}\in F[x]$ as well. When we evaluate at $u=\alpha$, we obtain $s_{i}(\alpha)=\pm a_{i}$, so $g(\alpha_{1},\dots,\alpha_{n})=\tilde{g}(s_{1}(u),\dots,s_{n}(u))$ must also be in $F$. $\square$

## Splitting Fields

> [!theorem] Splitting Theorem
> Let $K\supset F$ be a splitting field extension of a polynomial $f \in F[x]$. If an irreducible polynomial $g\in F[x]$ has one root in $K$, then it splits completely in $K$. 
> 

## The Discriminant

