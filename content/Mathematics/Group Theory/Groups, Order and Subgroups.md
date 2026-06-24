---
completed: true
updated: 2026-06-24
---
## Groups

>[!definition] Group
> A *group* is a set $G$ together with a composition law $\circ: G \times G \rightarrow G$ such that the following properties hold:
>- Associativity: $(a \circ b) \circ c = a \circ (b \circ c)$ for all $a,b,c \in G$.
>- Identity: there exists $e \in G$ such that $e \circ a = a \circ e = a$ for all $a \in G$.
>- Inverse: for every $a \in G$ there exists $b \in G$ such that $a \circ b = b \circ a = e$.
>
>We may sometime denote the group by $(G,\circ)$ to emphasize the law of composition. ^6e0960

> [!remark]+
> Whilst the definition of associativity involves only three elements it implies the generalized associative law, that is, a product of $n$ elements in a group $a_1a_2 · · · a_n$ has the same value regardless of any parentheses.
> 

>[!proposition] 
>Let $G$ be a group. Then
>1. For any $a \in G$, the inverse is unique and denoted $a^{-1}$.
>2. For any $a \in G$, $(a^{-1})^{-1} = a$.
>3. $(ab)^{-1} = b^{-1}a^{-1}$.
>4. In $G$ the cancellation laws holds: for $a,b,c \in G$, $ab=ac$ implies that $b=c$.
>$\quad$

*Proof*
1. If $b$ and $c$ are both inverses of $a$, then $b = be = b(ac) = (ba)c = ec = c$. Hence the inverse is unique;
2. $(a^{-1})^{-1}$ is the inverse of $a^{-1}$, so it must be $a$ by the uniqueness of inverses;
3. $b^{-1}a^{-1}$ is the inverse of $ab$, since $(ab)(b^{-1}a^{-1}) = a(bb^{-1})a^{-1} = aea^{-1} = aa^{-1} = e$ and $(b^{-1}a^{-1})(ab) = b^{-1}(a^{-1}a)b = b^{-1}eb = b^{-1}b = e$;
4. If $ab=ac$, then $a^{-1}(ab) = a^{-1}(ac)$, so $b=c$. 

$\square$

## Subgroups and Order

> [!definition] Abelian Group
> A group is called *abelian* if the composition law is commutative. ^6d511a

> [!definition] Finite Group
> A group is called *finite* if $G$ is a finite set; otherwise the group is called *infinite*. The order of a finite group is the number of elements in a finite group, denoted $|G|$. ^3bce31

> [!definition] Power & Order of an Element
> For an element $a$ and in a group $G$ and $n \in \N$ we write $a^{n}$ for the unambiguous composition of $a$ with itself $n$ times (this follows from generalized associativity). 
> We also define $a^{0} := e$ and $a^{−n} = (a^{−1})^n$.
> An element $g \in G$ has *finite order* if there is $n \in \N$ such that $g^n = e$; the minimal such $n$ is the *order* of $g$ and denoted $o(g)$. Otherwise we say that $g$ has *infinite order*.

> [!proposition] Laws of Exponents
> Let $G$ be a group, let $a, b ∈ G$ , and let $m$ and $n$ be integers. Then
> 1. If $a$ and $b$ commute, then $(ab)^n = a^nb^n$.
> 2. $a^ma^n=a^{m+n}$.
> 3. $(a^n)^m = a^{mn}$.
> $\quad$

*Proof*  
1. If $a$ and $b$ commute, then $(ab)^n = (ab)(ab)\cdots(ab)= a^nb^n$;
2. $a^ma^n = a\cdots a a\cdots a = a^{m+n}$;
3. $(a^n)^m = (a^n)(a^n)\cdots(a^n) = a^{mn}$. 

$\square$

> [!definition] Subgroup
> Let $G$ be a group, a nonempty subset $H \subset G$ is called a *subgroup* of $G$ if it is a group under the same law of composition of $G$. In such case we write $H \leq G$. ^1ccb07

> [!proposition]
> A nonempty subset $H \subset G$ is a subgroup if and only if it is closed under composition and under taking inverses. That is $a,b \in H \implies ab \in H$ and $a \in H \implies a^{-1} \in H$. The latter two can be consolidated to $a,b \in H \implies ab^{-1} \in H$.

<u><b>e.g.</b></u>  All subgroups of $(\Z,+)$ are of the form $n\Z$ for some $n \in \N$. This is easy to see since if $H$ is a nontrivial subgroup, then it contains some non-zero integer $m$. If $m < 0$ we can replace it by $-m$. Let $n$ be the smallest positive integer in $H$, then any element $h$ in $H$ must be a multiple of $n$, otherwise the division algorithm gives $h = qn + r$ with $0 < r < n$, hence $r = h - qn \in H$, contradicting the minimality of $n$. Thus, $H = n\Z$.

> [!corollary]
> If $H\leq G$, $K\leq G$, then $H\cap K\leq G$.

*Proof*  Immediate from the above propostion. $\square$
