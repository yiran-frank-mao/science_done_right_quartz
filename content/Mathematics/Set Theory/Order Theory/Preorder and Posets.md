>[!definition] Poset
>A poset is a set $A$ equipped with a binary relation $a \leq_{A} b$ such that the following conditions hold for all $a, b, c ∈ A$:
>- reflexivity: $a ≤_{A} a$
>- transitivity: if $a ≤_A b$ and $b ≤_{A} c$, then $a ≤_{A} c$
>- antisymmetry: if $a≤_{A} b$ and $b≤_{A} a$, then $a=b$.
>$\quad$^33ba5a

<u><b>e.g.</b></u> The [[Number Systems#^5fea5c|real numbers]] $\R$ with their usual ordering $x ≤ y$ form a partially ordered set that is also linearly ordered: either $x ≤ y$ or $y ≤ x$ for any $x, y$.

>[!definition] 
>**Def**  <i><u>Monotone Poset Function</u></i>
>A function $m\colon A\to B$ with posets $A$ and $B$ is monotone if $$a\leq_Ab\implies m(a)\leq_{B}m(b)$$ ^893616
