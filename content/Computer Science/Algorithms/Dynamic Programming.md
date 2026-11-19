---
created: 2023-11-04
updated: 2025-02-12
cssclasses:
  - img-grid
  - img-zoom
tags:
  - recursion
completed: true
---
> [!definition] Dynamic Programming Problem
> A given problem $P$ is a dynamic programming problem if
> - **Optimal Substructure:** The optimal solution to the problem is formed by optimal solutions to sub-problems.
> - **Overlapping Sub-problems:** Some of the sub-problems are the same, and therefore if we remember the solution, we only need to solve these sub-problems once.
> $\quad$

## Chain Matrix Multiplication

> [!definition] Chain Matrix Multiplication Problem
> Given a chain of matrices $A_{p_0\times p_1}A_{p_1 \times p_2}\dots A_{p_{n-1}\times p_n}$ decide which order should we multiply this chain of matrices such that total number of arithmetic operations is minimized.

> [!proposition]
> The time complexity of computing $A_{p\times r}B_{r\times q}$ is in $\Theta(prq)$.

> [!algorithm]
> **Algorithm** Consider a 2-dimensional table $m_{n\times n}$, where $m[i,j]$ for $1\leq i\leq j\leq n$ is the optimal cost for computing. We do not care about the values for $j< 𝑖$. Then
> $$ m[i,j]=\begin{cases}
> 0, & \quad i=j \\ \min_{i\leq k \leq j-1}\{ m[i,k]+m[k+1,j]+p_{i-1}p_kp_j \} & \quad i<j
> \end{cases} $$
> As the base case we set $𝑚 [𝑖, 𝑗] = 0$ for all $1 ≤ 𝑖 = 𝑗 ≤ 𝑛$. Then loop over $1 ≤ 𝑖 < 𝑗 ≤ 𝑛$ in the order of $j-i$ (i.e. $[1,2] \to [2,3] \to [3,4] \to \dots \to [1,n-1] \to [2,n] \to [1,n]$). Finally, output $m[1,n]$.

> [!proposition]
> The time complexity of the above algorithm is in $𝑂(𝑛^3)$.
> **Proof**  We spend at most $O(n)$ for each entry of the table and iterate half of the table entries which is in $O(n^2)$. Thus the overall time complexity is in $O(n^3)$.

## Longest Increasing Subsequence(LIS)

> [!definition] Longest Increasing Subsequence Problem
> Given an array $a$ of size $𝑛$, the task is to find the length of the longest increasing subsequence that is, the longest possible subsequence in which the elements of the subsequence are sorted in increasing order.
> <b><u>e.g.</u></b> The LIS of sequence $[3,10,2,1,20]$ is $[3,10,20]$.

> [!algorithm]
> Let $L[i]$ be the length of LIS of $a[0:i]$. Then $L[i]$ can be determined recursively:$$ L[i] = 1 + \max_{1\leq j <i \\ } \{ L[j] \mid a[j]\leq a[i] \},\quad L[0]=1 $$Then solve it by dynamic programming.

> [!proposition]
> The time complexity of the above algorithm is in $O(n^2)$.


## Longest Common Subsequence

> [!definition] Longest Common Subsequence
> Given two strings, $𝑆_1$ and $𝑆_2$, the task is to find the the longest subsequence present in both strings.

> [!algorithm]
> **Algorithm** Let $L[i,j]$ be the length of LCS of $S_1[0:i]$ and $S_2[0:j]$. Then $L[i,j]$ can be determined recursively:
> $$ L[i,j]= \left \{ \begin{aligned} & L[i-1,j-1]+1 & \quad & \text{if $S_1[i]=S_2[j]$} \\ & \max \{L[i-1,j],L[i,j-1]\} & \quad & \text{otherwise} \end{aligned} \right. $$
> where initially $L[-1,j]=0$ and $L[i,-1]=0$ for all indices $i,j$.
> Then solve it by 2-dimensional dynamic programming.
> 
> ![lcs1](https://i.imgur.com/atIjK86.png)![lcs2](https://i.imgur.com/u87z7da.png)

> [!proposition]
> The table has $(𝑚 + 1)×(𝑛 + 1)$ entries, thus the time complexity is in $\Theta (m\times 𝑛)$.
