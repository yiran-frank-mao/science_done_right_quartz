**Fact** _Imposing Relations_
We interpret the quotient $R/(a_1,\dots,a_n)$ as imposing the relations $a_1=a_2=\dots=a_n=0$ or ‘killing’ the elements $a_i$. Killing the elements $a_i$ in installments and in various orders, or in one strike lead to the same result. That is, we have following commutative diagram:

<img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/imposing_relations.svg" alt="imposing_relations" style="width:30%;">

> [!comment] Adjoining Elements
> A primary tool for constructing new rings is to take a ring $R$ and a ‘free’ variable and create the polynomial ring, and then quotient by a polynomial. We show see this further in [[Fields Construction#Adjoining Roots|field extensions by adjoining roots of polynomials.]]

<u><b>e.g.</b></u>  The complex numbers are constructed from $\R$ by setting $\mathbb{C} := \R[x]/(x^2+1)$. In fact, we can define $\varphi : \mathbb{C} \to \R[x]/(x^2+1), a+bi \mapsto \overline{a+bx}$. Clearly it is surjective and injective. Since $$ \begin{align}
\varphi(a+bi)\varphi(c+di)&=\overline{ac+(ad+bc)x+bdx^2} \\
&=\overline{(ad+bc)x-bd+ac} \\
&=\varphi((ad+bc)i+(ac-bd)) \\
&=\varphi((a+bi)(c+di)),
\end{align} $$$\varphi$ is homomorphism, yielding a isomorphism. ^a4b259

> [!proposition]
> If $f$ in $R[x]$ has no root in $R[x]$ we can form the quotient $R[x]/\left(f (x)\right)$ and $\overline{x} = x +(f (x))$ is a root of $f$.

> [!definition]
> Whenever we have a subring $R$ of a ring $S$ and an element $α ∈ S$ we denote by $R[α]$ the smallest subring of $S$ that contains $R$ and $α$.

> [!proposition]
> $\Phi:R[x] \to S, f \mapsto f(\alpha)$ defines an isomorphism $R[x]/\ker(\Phi)\cong R[\alpha]$.

## **Field of Fractions & Product Rings**

> [!definition] The Field of Fractions
> Suppose $R$ is an [[Ring, Field and Integral Domain#^domain|integral domain]]. Consider $R\times(R \backslash \{0\})=\{ (a,b)\mid a,b \in R, b\neq0 \}$ equip with the following relation: $$ (a_1,b_1)\sim(a_2,b_2) \quad \text{if} \quad a_1b_2=a_2b_1 $$
> This is an [[Relations and Functions#^14741d|equivalence relation]]. Let $\frac R$ denote the quotient. We denote the equivalence classes by $a/b = [(a,b)]$.

> [!proposition]
> $\frac R$ is a field.
> 

> [!theorem]
> Suppose $R$ is an integral domain and $F$ is defined as above. Define addition and multiplication on $F$ by$$ a/b \cdot c/d = ac/bd, \quad a/b + c/d = (ad+bc)/bd $$Then $F$ is a field, denotes as $\text{Frac}(R)$. The map $R \to F$ given by $a \mapsto \frac{a}{1}$ is an injective ring homomorphism.

**e.g.** If $R=\Z$ then $\text{Frac}(R)=F =\mathbb{Q}$. If $R=E[x]$, for a field $E$, then the field of fraction of $E[x]$, denoted $E(x)$, is called the field of rational functions over $E$:

$$ E(x) = \{ f/g=[(f,g)] \mid f,g \in E[x], g\neq 0 \} $$

**Def** _Product Rings_
Let $R_1 , R_2$ be rings. Then $R_1 × R_2$, with coordinate-wise addition and multiplication, is a ring with zero $(0, 0)$ and identity element $(1, 1)$.

## Prime and Maximal Ideals

> [!definition] Prime Ideal
> Let $R$ be a ring. An ideal $P \triangleleft R$ is prime if $P \neq R$ and $ab \in P$ implies that either $a \in P$ or $b \in P$. ^da4561

> [!theorem]
> Let $R$ be a ring. $P \triangleleft R$ is prime if and only if $R/P$ is an integral domain.
> 

> [!definition] Maximal Ideal
> Let $R$ be a ring. An ideal $M \triangleleft R$ is maximal if $M \neq R$ and there is no other ideal $I$ such that $M \subsetneq I \subsetneq R$. ^ee0592

<u><b>e.g.</b></u> $M \triangleleft \Z$ is maximal iff $M =(p)=p\Z$ for a prime $p$. In general, we have the following proposition holds:

> [!proposition]
> Let $R$ be a principle ideal domain, then $(a) \triangleleft R$ is maximal if and only if $a$ is irreducible.

*Proof*  In a PID, we have that $(a)\subset(b)$ iff $b \mid a$. It follows that $(a)$ is maximal iff there is no proper divisor $b\mid a$, which means $a$ is irreducible. $\square$

> [!corollary]
> If $F$ is a field, then $M = (f (x)) \triangleleft F [x]$ is maximal iff $f (x)$ is irreducible.

*Proof*  $F[x]$ is a PID, so $(f(x))$ is maximal iff $f(x)$ is irreducible. $\square$

> [!theorem]
> Let $I \triangleleft R$ be an ideal. Then $I$ is maximal iff $R/I$ is a [[Ring, Field and Integral Domain#^575174|field]].

> [!corollary]
> Every maximal ideal is prime.

*Proof*  Every field is an integral domain. $\square$


**Corollary** Let $f\in F[x]$ be an irreducible polynomial. Then $F[x]/(f(x))$ is a field and contains a root of $f$, namely the coset $\overline{x} = x + (f(x))$.