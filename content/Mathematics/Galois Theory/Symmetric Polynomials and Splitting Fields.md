> The more symmetric $\alpha$ is, the closer it is to the base field $F$.

## Symmetric Polynomials

> [!definition] Symmetric Polynomials
> A polynomial $f(x_{1},x_{2},\dots,x_{n})\in R[x_{1},\dots x_{n}]$ for some unital commutative ring $R$ is *symmetric* if it is unchanged when permuting the variables. That is, $f(x_{\sigma(1)},x_{\sigma(2)},\dots,x_{\sigma(n)})=f(x_{1},x_{2},\dots,x_{n})$ for all $\sigma\in S_{n}$.
> The following special symmetric polynomials in $n$ variables are called *elementary*:
> $$e_{k}(x_{1},\cdots, x_{n}) = \sum_{1\leq a_{1}<a_{2}<\cdots a_{k}\leq n} x_{a_{1}}x_{a_{2}}\cdots x_{a_{k}}, \qquad k=1,\cdots, n.$$
> The set of all symmetric polynomials in $n$ variables with coefficients in $R$ is denoted by $R[x_{1},\dots,x_{n}]^{S_{n}}$.

<u><b>e.g.</b></u>
- $x_{1}^{3}+x_{2}^{3}-235$, $x_{1}x_{2}x_{3}-2x_{1}x_{2}-2x_{1}x_{3}-2x_{2}x_{3}$ are symmetric;
- $x_{1}-x_{2}$, $x_{1}^4x_{2}^2+x_{3}^4x_{4}^2$ are not symmetric;
- $e_{1}(x_{1},x_{2},x_{3})=x_{1}+x_{2}+x_{3}$, $e_{2}(x_{1},x_{2},x_{3})=x_{1}x_{2}+x_{1}x_{3}+x_{2}x_{3}$, $e_{3}(x_{1},x_{2},x_{3})=x_{1}x_{2}x_{3}$.


> [!theorem] Fundamental Theorem of Symmetric Polynomials
> Every symmetric polynomial $f(x_{1},x_{2},\dots,x_{n})\in R[x_{1},\dots x_{n}]$ with coefficients in a ring $R$ can be written in a unique way as a polynomial of elementary symmetric polynomials.
> More conceptually, this means that the $R$-algebra homomorphism 
> $$ \Phi\colon R[t_{1},\cdots, t_{n}] \to R[x_{1},\cdots, x_{n}]^{S_{n}},\qquad t_{k}\mapsto e_{k} $$ 
> is an isomorphism. In particular, $R[x_{1},\cdots, x_{n}]^{S_{n}}$ is itself a free polynomial algebra over $R$. ^fc4c03

*Proof*  There is nothing to show when $n =1$, because every polynomial is symmetric, and $f(x_{1})=f(e_{1}^{1})$ in that case (we abbreviate $e_{k}(x_{1},\dots, x_{n})$ with $e_{k}^{n}$). Proceeding by induction, we assume the theorem proved for symmetric polynomials in $n-1$ variables. Now given a symmetric polynomial $g(x_{1},\cdots, x_{n})$, let $\bar{g}(x_{1},\cdots, x_{n-1}):=g(x_{1},\cdots, x_{n-1},0)$, then $\bar{g}$ is symmetric in $n-1$ variables. So by the hypothesis, $\bar{g}$ can be written as a polynomial $h(e_{1}^{n-1}, \cdots,e_{n-1}^{n-1})$. Consider the difference $g(x_{1},\cdots,x_{n})-h(e_{1}^{n}, \cdots,e_{n-1}^{n})$, this is a symmetric polynomial in $n$ variables, and if we set $x_{n}=0$, we get zero. Therefore, $x_{n}$ divides this difference, and by symmetry, $x_{i}$ divides it for all $i=1,\cdots,n$. Thus, we can write $$g(x_{1},\cdots,x_{n})-h(e_{1}^{n}, \cdots,e_{n-1}^{n})=x_{1}x_{2}\cdots x_{n}k(x_{1},\cdots,x_{n})=e_{n}^{n}k(x_{1},\cdots,x_{n})$$for some symmetric polynomial $k$. Rearranging, we have $g(x_{1},\cdots,x_{n})=h(e_{1}^{n}, \cdots,e_{n-1}^{n}) + e_{n}^{n} k(x_{1},\cdots,x_{n})$. Note that $k$ has strictly lower degree than $g$, so we can perform a second induction to conclude that $k$ can be expressed as a polynomial in $e_{1}^{n},\cdots,e_{n}^{n}$. Therefore, $g$ can be expressed as a polynomial in $e_{1}^{n},\cdots,e_{n}^{n}$. The uniqueness of the expression follows from the fact that distinct monomials in the elementary symmetric polynomials necessarily have distinct leading monomials in the original variables^[The proof of uniqueness is tedious and similarly by inductions. One can refer to [the wikipedia page](https://www.wikiwand.com/en/Elementary_symmetric_polynomial) for detailed proofs]. $\square$

Maybe the proof is not very clear, but the following example shows all the steps in the proof:

<u><b>e.g.</b></u>  Let $g(x_{1},x_{2},x_{3},x_{4}):=x_{1}x_{2}^{2}+x_{1}x_{3}^{2}+x_{1}x_{4}^{2}+x_{2}x_{1}^{2}+x_{2}x_{3}^{2}+x_{2}x_{4}^{2}+x_{3}x_{1}^{2}+x_{3}x_{2}^{2}+x_{3}x_{4}^{2}+x_{4}x_{1}^{2}+x_{4}x_{2}^{2}+x_{4}x_{3}^{2}$, then $\bar{g}(x_{1},x_{2},x_{3})=g(x_{1},x_{2},x_{3},0)=x_{1}x_{2}^{2}+x_{1}x_{3}^{2}+x_{2}x_{1}^{2}+x_{2}x_{3}^{2}+x_{3}x_{1}^{2}+x_{3}x_{2}^{2}$, which can be expressed as $h(e^{3}_{1},e^{3}_{2},e^{3}_{3})=e^{3}_{1}e^{3}_{2}-3e^{3}_{3}$, where $e^{3}_{1}=x_1+x_2+x_3$, $e^{3}_{2}=x_1 x_2+x_1 x_3+x_2 x_3$, and $e^{3}_{3}=x_1 x_2 x_3$. Then we have $$g(x_1,x_2,x_3,x_4)-h(e^{4}_{1},e^{4}_{2},e^{4}_{3})=k(x_1,x_2,x_3,x_4)e^{4}_4.$$Note that $g$ has degree $3$, so $k=0$, thus $g(x_{1},x_{2},x_{3},x_{4})=h(e^{4}_{1},e^{4}_{2},e^{4}_{3})=e^{4}_{1}e^{4}_{2}-3e^{4}_{3}$, we are done.

> [!corollary]
> Suppose that a polynomial $f(x)=x^{n}+a_{1}x^{n-1}+\dots+ a_{n}$ has coefficients in a [[Ring, Field and Integral Domain#^575174|field]] $F$, and it splits completely in an extension field $K$, with roots $\alpha_{1},\dots,\alpha_{n}$. Let $g(u_{1},\dots ,u_{n})$ be a symmetric polynomial in $u_{1},\dots ,u_{n}$ with coefficients in $F$. Then $g(\alpha_{1},\dots,\alpha_{n})\in F$. 

*Proof*  [[Symmetric Polynomials and Splitting Fields#^fc4c03|Symmetric functions theorem]] tells that $g$ is a polynomial in the elementary symmetric functions. Say that $g(u_{1},\dots,u_{n})=\tilde{g}(s_{1}(u),\dots,s_{n}(u))$, where $\tilde{g}\in F[x]$ as well. When we evaluate at $u=\alpha$, we obtain $s_{i}(\alpha)=\pm a_{i}$, so $g(\alpha_{1},\dots,\alpha_{n})=\tilde{g}(s_{1}(u),\dots,s_{n}(u))$ must also be in $F$. $\square$

## Splitting Fields

> [!definition] Splitting Field
> A *splitting field* of a polynomial $f\in F[x]$ is a field extension $K$ of $F$ such that no proper subfields of $K$ can make $f$ split completely.
> 

^concept-12eecb935785

> [!proposition]
> Splitting fields are unique up to 
> 

<u><b>e.g.</b></u>  $f(x)=x^{p}-1\in F[x]$, 

> [!theorem] Splitting Theorem
> Let $K\supset F$ be a splitting field extension of a polynomial $f \in F[x]$. If an irreducible polynomial $g\in F[x]$ has one root in $K$, then it splits completely in $K$. 
> 


## The Isomorphism Lifting Lemma

Given a field isomorphism $\varphi\colon F\to F'$, we can naturally lift it to an isomorphism $\varphi_{*}\colon F[x] \to F'[x]$ by $$\varphi_{*}(a_{k}x^{k}+a_{k-1}x^{k-1}+\cdots+a_{0}):=\varphi(a_{k})x^{k}+\varphi(a_{k-1})x^{k-1}+\cdots+ \varphi(a_{0}).$$Armed with this new notation, we can now state the result:

> [!lemma] Isomorphism Lifting Lemma
> Suppose $f\in F[x]$ and $\varphi\colon F\to F'$ is an isomorphism of fields. Let $K$ and $K'$ be splitting fields of $f$ and $\varphi_{*}(f)$ over $F$ and $F'$ respectively. Then
> 1. $[K:F]=[K':F']=:n$;
> 2. there exists one, but at most $n$, isomorphisms $\tilde{\varphi}\colon K\to K'$ such that $\tilde{\varphi}|_{F}=\varphi$.

*Proof*  
