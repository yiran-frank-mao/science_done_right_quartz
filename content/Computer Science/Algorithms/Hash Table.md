---
updated: 2025-08-26
completed: true
---
A *hash table* is a data structure that allows you to quickly store and retrieve data using a key, making operations like searching, inserting, and deleting very fast on average. It is widely used in real-world applications where speed is critical. For example, programming languages use hash tables to implement dictionaries or maps, letting developers associate values with unique keys. Web browsers rely on them for caching, so frequently visited websites load faster. Databases use hash tables for indexing, enabling quick lookups of records. Even compilers use them to manage symbol tables, keeping track of variable and function names efficiently.

> [!definition] Hash Table
> A *hash table* is defined with a universe $U=\{k_1, \dots, k_u \}$, an array $T$ of size $m$, with $n$ currently stored keys. And a hash function $h\colon U \to \{0, \dots, m-1 \}$, such that $|T| =m ≪ \max_{k∈U} k$. Each slot in the hash table contains a linked list. For insertion, if a key is hashed into a non-empty slot, place the new pair (key plus satellite data) at the front of the respective list.

## **Hash Functions**

> [!definition] Uniform Hash Function
> A *uniform hash function* is a function where any given key is equally likely to map onto any of the m slots, independently of where any other key has been mapped to. Thus, it is a function h such that: $$  P[h(k):=v]=\frac{1}{m}  $$

> [!proposition]
> Given a uniform hash function and assuming the input keys are uniformly distributed and independent, we get the following collision probability:
> $$  P[h(k)=h(k^\prime)]=\frac{1}{m},\quad k\neq k^\prime  .$$

> [!definition] Load Factor
> For a hash table with $n$ keys stored and $m$ slots, define $\alpha=\frac{n}{m}$ as the *load factor*.

> [!proposition] Time Complexity of Uniform Hashing
> Assume we use uniform hashing with chaining, $n$ is the number of keys stored, $m$ is the size of the array, $α=\frac{n}{m}$ is the load factor. Then Average time complexity of searching a key is in $\Theta(1 + α)$, while the worst is in $O(n)$.

## Universal Hashing

> [!definition] Universal Hash Functions
> Suppose we have $m$ slots in a hashtable. A collection of hash functions $H$ is called *universal* if for each pair of keys $k\neq k^\prime$, the number of hash functions for which $h(k)=h(k^\prime)$ is at most $\frac{|H|}{m}$. That is
> $$  |\{ h\in H \mid \exists k\neq k^\prime,h(k)=h(k^\prime) \}|\leq \frac{|H|}{m} . $$
> Equivalently, for each arbitrary $h ∈ H$, the probability of a hash collision between any distinct keys $k$ and $k^\prime$ is at most $\frac{1}{m}$. ^4c61bb

> [!algorithm] Universal Hashing
> In universal hashing, we choose a random hash function $h$ from a universal collection of hash functions $H$.

> [!definition] Dot Product Hash Family
> Assume $m$ is a prime number. Express key $k$ (which has base $10$) with base $m$. Then express $k$ as vector $\vec{k} = \langle k_{r −1} , \dots, k_0\rangle$ where $k_i \in \{0,\dots,m−1\}$ for all $0≤i≤r−1$, and $r = ⌊\log_m(\max_{k\in U} k)⌋ + 1$. Define:
> $$  h_a(k)=\left(\vec{a} \cdot \vec{k}\right) \mod m,$$where $\vec{a}=\langle a_{r-1},a_{r-2},\dots,a_0\rangle$ is a base $m$ vector.
> Then *dot product hash family* is $H=\{ h_a \mid a\in \{ 0,\dots,m^r-1\} \}$.

<u><b>e.g.</b></u> Suppose the possible keys are integers $U = \{0, \dots , 20\}$ and array size $m=5$. So we get $r=\lfloor \log_5(20) \rfloor + 1=2$. Assume pick $a=15\in \{ 0,\dots,5^2-1 \}$. Then $\vec{(a)}_m = \langle 3,0 \rangle_5$. Assume we have $k=19=3\cdot5^1+4\cdot5^0=\langle 3,4\rangle_5$. Hence we get $h_a(k)=h_{15}(19)= 9 \mod 5 =4$.

> [!proposition]
> The dot product hash family is [[Hash Table#^4c61bb|universal]].

## Open Addressing

*Open addressing* (also called *closed hashing*) is a collision-resolution technique used in hash tables where all items are stored directly within the table's array. When a collision occurs (i.e., two keys map to the same index), the algorithm probes the table to find another available slot instead of using an external structure like a linked list.

> [!definition] Open Addressing & Probe Sequence
> In *open addressing*, hash function becomes a map $h\colon U \times \{0,\dots,m-1 \} \to \{0,\dots,m-1 \}$. 
> The sequence $\langle h(k,0),h(k,1),\dots,h(k,m-1) \rangle$ is called a *probe sequence*.

> [!proposition]
> Each probe sequence must be a [[Permutations and Symmetric Groups#^caba60|permutation]] of $(0, . . . , m − 1)$.

> [!algorithm] Linear Hashing
> The linear hashing strategy is to simply define
> $$  h(k,i)=(h^\prime(x)+i)\mod m , $$
> where $h^\prime$ is a usual hash function.

> [!algorithm] Double Hashing
> The double hashing strategy is to combine two hash functions together such that
> $$  h(k,i)=\left( h_1(k) + i\cdot h_2(k)\right) \mod m  $$
> where $h_1$ and $h_2$ are usual hash functions satisfying $h_2\neq 0 and \gcd(h_2(k),m)=1$.

## Perfect Hashing

> [!definition] Bi-Level Hashing
> We call a data structure *bi-level hashing* if each slot of the hash table points to another hash table, and universal hashing is used in both levels.

> [!theorem]
> Suppose $n$ is the number of data. Let the number of slots m be $n^2$. The probability that there are any collisions (using a hash function randomly chosen from a set of universal hash functions) is strictly less than $\frac{1}{2}$.

*Proof*  There exist ${n \choose 2}$ pairs of keys (worst case number of collisions). And each collision has probability of $\frac{1}{m}$. Let X be a [[Random Variable and Probability Space#^a0b9ff|random variable]] counting the number of collisions. Then: $$  E[X]= {n \choose 2} \cdot \frac{1}{m} = \frac{1}{2}. $$$\square$

> [!algorithm] Build Bi-Level Hashing
> Bi-level hashing can be built as follows:
> 1. Set up outer hash table: $m :=n$, pick a universal hash function $h_1\in H$.
> 2. Set up inner hash tables:
> 	1. $m_i=n_i^2$ 
> 	2. If $\sum_{i=0}^{m-1} m_i > c\cdot n$ for a selected constant $c>0$, then redo the initial step.
> 	3. Choose a universal hash function $h_2^i ∈ H$ to be the hash function for this inner hash table at position $i$ and insert its elements. 
> 	4. As long as there are two $k\neq k^\prime$ with $h_2^i (k)=h_2^i (k^\prime)$, pick a different $h_2^i$ and rehash those elements in that inner table according to the new function.
>  $\quad$