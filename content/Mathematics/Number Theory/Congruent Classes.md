---
created: 2024-01-10
updated: 2024-09-17
---
**Def**  <i><u>Congruent Modulo</u></i>
We say that two integers $a$ and $b$ are congruent modulo $n$ if they give the same residue upon devision by $n$. All the following are equivalent:
$$
a \equiv b {\pmod{n}}\iff 
a-b\in n \mathbb{Z} 
$$
**Prop**  Congruent modulo is an [[Relations and Functions#^14741d|equivalence relation]].

**Def**  <i><u>Congruent Class</u></i>
The congruent class of an integer $a$ modulo an integer $n>1$ is the set of all integers such that $x\equiv a \mod n$: $$[a]=\{x\in\Z\mid x\equiv a \mod n\}$$**Prop**  Congruent class is an equivalence class.

**Def**  <i><u>$(\Z_n, +)$</u></i>
Define the group of $n$-congruent class with $[a]+[b]:=[a+b]$:
$$
\mathbb{Z}_{n}:=\{[0],[1],\cdot\cdot\cdot,[n-1]\}=\{a+n\mathbb{Z}\mid a\in\mathbb{Z}\}
$$
**Prop**  $\Z_n$ is a cyclic group.

**Def**  <i><u>$(\Z_n^\times, \cdot)$</u></i>
Let $n \in \N$. Define with $[a]\cdot[b]:=[a\cdot b]$
$$
\mathbb{Z}_{n}^{\times}:=\{[k]\mid(k,n)=1\}\subset\mathbb{Z}_{n}
$$
**Prop**   $\Z_n^{\times}$ is a group.
**Proof**  For all $[a],[b],[c] \in \Z_n^{\times}$, we have
$$
([a][b])[c]= [abc]=[a][bc]=[a]([b][c])
$$
And exists $[1]$ as an identity as $[a][1]=[a]$. Since there exist integers $x,y \in \Z$ such that $ax+yn=1$ which by taking residue modulo gives $[a][x]=[x][a]=[1]$
<b><u>e.g.</u></b>   $\Z_8^{\times}=\{[1],[3],[5],[7] \} \cong K_4$

**Prop**  $\Z_n^{\times} \cong \mathop{\text{Aut}}(\Z_n)$

**Def**  <i><u>Multiplicative Order</u></i>
Let $a$ be an integer number coprime to a prime number $p$. The multiplicative order of $a$ modulo $p$ or $[a]$ is the least positive integer $d$ such that $a^{d}\equiv 1\mod p$. The multiplicative order is equivalent to the order of $[a]$ in group $\Z_{p}^{\times}$.

**Def**  <i><u>Euler $\varphi$-Function</u></i>
Let $n\in\N$. Euler $\varphi$ function is defined to be:
$$
\varphi(n)=|\{1\leq k\leq n\mid(n,k)=1\}|=|Z_{n}^{\times}|
$$