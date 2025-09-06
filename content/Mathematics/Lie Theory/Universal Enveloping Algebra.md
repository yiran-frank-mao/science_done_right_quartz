## Poincaré–Birkhoff–Witt Theorem

> [!definition] Universal Enveloping Algebra
> A *universal enveloping algebra* of a [[Lie Algebra#^5007ba|Lie algebra]] $L$ is a pair $(U(L),i)$ where $U(L)$ is a Lie algebra that is also a [[Non-Commutative Rings#^2c3d07|unital associative algebra]] with the standard Lie bracket (i.e. commutator of multiplication), and $i\colon L\to U(L)$ is a Lie algebra homomorphism. 
> It satisfies the following universal property: for any associative algebra $A$ with the standard Lie  bracket and any Lie algebra homomorphism $\phi\colon L\to A$, there exists a unique associative algebra homomorphism $\tilde{\phi}\colon U(L)\to A$ such that the following diagram commutes:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/universal_enveloping_algebra.svg" alt="universal_enveloping_algebra" style="width:25%;"/>
> In other words, $U(L)$ is the "most general" associative algebra that $L$ can map to via Lie algebra homomorphisms.

The existence and description of universal enveloping algebras is given by the Poincaré–Birkhoff–Witt theorem:

> [!theorem] Poincaré–Birkhoff–Witt Theorem
> Suppose $L$ is a [[Lie Algebra#^5007ba|Lie algebra]] over $F$ with a [[Order#^a8688d|totally ordered]] basis $\{X_{1},X_{2},\cdots\}$. Then its universal enveloping algebra $U(L)$ exists and has a basis consisting of the ordered monomials. That is, the set of all elements of the form $x_{i_1}^{e_1}\ldots x_{i_n}^{e_n}$ for $i_{1}<i_{2}<\cdots<i_{n}$ and integers $e_{1},\ldots,e_{n}> 0$ is a basis of $U(L)$.

> [!corollary]
> The canonical map of a Lie algebra to its universal enveloping algebra is an [[Relations and Functions#^042daf|injection]].

## Modules over a Lie Algebra

Now, every Lie algebra has a universal enveloping algebra, which is in particular a ring. So we can talk about modules over it:

> [!definition] Module over a Lie Algebra
> Suppose $L$ is a [[Lie Algebra#^5007ba|Lie algebra]] over a [[Ring, Field and Integral Domain#^575174|field]] $F$. A *module over $L$* is a [[Modules#^697aa9|module]] over its universal enveloping algebra $U(L)$. 
> Specifically, it is an $F$-[[Vector Spaces#^f4b63e|vector space]] $M$ together with a scalar multiplication $L\times M\to M$, $(x,v)\mapsto x\cdot v$ satisfying:
> - $(ax+by) \cdot v= a(x\cdot v) + b(y\cdot v)$;
> - $x\cdot (av + bw) = a (x\cdot v) + b(x\cdot w)$;
> - $[x,y]\cdot v = x\cdot (y\cdot v) - y\cdot (x\cdot v)$,
> 
> for all $x,y\in L$, $v,w\in M$ and $a,b\in F$.

> [!remark]+ Modules over a Lie algebra are Exactly Representations
> A representation of a [[Lie Algebra#^5007ba|Lie algebra]] $L$ is a homomorphism $\rho\colon L\to \gl (V)$ for some [[Vector Spaces#^f4b63e|vector space]] $V$. This is equivalent to giving $V$ the structure of a module over $L$ by defining $x\cdot v := \rho(x)(v)$ for $x\in L$ and $v\in V$. Therefore, we shall often use the terms "module over a Lie algebra" and "representation of a Lie algebra" interchangeably.