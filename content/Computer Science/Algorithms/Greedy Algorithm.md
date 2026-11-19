**Def**  <i><u>Greedy Algorithm</u></i>
The greedy algorithm makes locally optimal choices and may lead to a globally optimal solution.

**Fact**  <i><u>Requirements of Greedy Algorithm</u></i>
- **Optimal Sub-Structure:** Optimal solution to the problem is formed by optimal solutions to sub-problems.
- **Greedy-Choice Property:** A globally optimal solution can be formed from locally optimal solutions.

**Fact**  Generally, greedy algorithms are faster than dynamic programmings.

**Prop**  Any problem that can be solved by greedy can also be solved by dynamic programming.

## Activity Selection Problem

**Def**  <i><u>Activity Selection Problem</u></i>
Consider a set of activities $S=\{ a_1,a_2,\dots,a_n \}$. Each activity $a_i$ takes place on the interval $[s_i,f_i)$. And we call $a_i$ and $a_j$ are compatible if $[s_i,f_i) \cap [s_j,f_j)=\varnothing$. Find the largest subset of $𝑆$ consisting of mutually compatible activities.

**Algorithm**
1. Sort the activities based on the starting points, give $S_s$
2. Sort the activities based on the finish points, give $S_f$
3. Start with an empty set $A$
4. While $𝑆$ is not empty:
    1. Find the activity $a_m$ with the $f_m=\min_if_i$ and add it to $A$
    2. Remove any activity in $𝑆$ which overlaps with $𝑎_m=[s_m,f_m]$ using $S_s$ and $S_f$
5. Return $A$

**Proof**  Consider a set of activities $S$. Let $a_m\in S$ such that $m=\argmin_i f_i$. Claim that there exists an optimal solution $A$ such that $a_m\in A$. Suppose $A$ is some optimal solution. Let $a_k \in A$ such that $k=\argmin_{[s_i,f_i]\in A}f_i$. Since $A\subseteq S$, $f_m\leq f_k$. Clearly $a_m \in A$ if $m=k$. Case $m\neq k$, then exists $A^\prime = (A\backslash\{a_k\})\cup\{a_m \}$ which is also an optimal solution.

**Prop** The overall time complexity of the above algorithm is in $\Theta(n \log n)$.