## Probabilistic Analysis of Deterministic Algorithms

**Algorithm**  <i><u>Insertion Sort</u></i>
```cpp
Insertionsort (A)
for j = 2 to A.length
	key = A[j]
	i = j-1
	while i > 0 and A[i] > key
		A[i+1] = A[i]
		i = i - 1
	A[i+1] = key
```

**Def**  <i><u>Inversion</u></i>
An inversion is a permutation on an array $A$ of the form $(i,j)$ such that $i<j$ but $a_i>a_j$.
<b><u>e.g.</u></b>  $A = [20, 5, 10, 8]$ has 4 inversions $(1,2); (1,3); (1,4); (3,4)$
**Prop** For an insertion sort, the best case has $0$ inversions, and the worst case has $\binom{n}{2}$inversions.

**Fact**  The goal of sorting is to remove inversions.

**Prop** In Insertion Sort, swapping a pair of numbers reduces the number of inversions by exactly $1$.

## **Probabilistic Analysis of Randomized Algorithms**
**Def**  <i><u>Randomized Algorithm</u></i>
A randomized algorithm is an algorithm whose behavior is determined not just by its input but also by random numbers. The behavior can vary even for the same input.

**Algorithm**  <i><u>Random Quick Sort</u></i>
1. Pick a random element in the array.
2. Split the array into two sub-arrays, one containing elements smaller than the random element and one containing elements larger than that.
3. Do the above two steps recursively for each sub-array until the sub-arrays have only 1 element.
```cpp
RandQuickSort (A, p, r)
	if p<r
		q = RandPartition(A, p, r) 
		RandQuickSort (A, p, q-1) 
		RandQuicksort (A, q+1, r)
	
RandPartition (A, p, r) 
	i =random(p, r)
	swap A[r] with A[i]
	return Partition(A, p, r)
	
Partition(A, p, r)
	x = A[r]
	i = p-1
	for j=p to r-1
		if A[j] <= x
			i = i+1
			swap A[i] with A[j]
	swap A[i+1] with A[r]
	return i+1
```

## Randomized Algorithms
**Fact**
1. Computing matrix computation takes $Θ(𝑛^3)$ for a trivial algorithm. It can also be done in $Θ(n^{2.37})$.
2. Computing matrix-vector computation takes $Θ(𝑛^2)$ for a trivial algorithm.

**Algorithm**  <i><u>Freivalds’s Algorithm</u></i>
Freivalds’s Algorithm is to verify the input matrices $A,B,C$ if they satisfy that $AB=C$.
1. Generate an $𝑛\times 1$ random $0/1$ vector $\vec{r}$
2. Compute $𝑃 = 𝐴 \times (B \times \vec{r}) − 𝐶 \vec{r}$
3. Output **Yes** if $P$ is equal to zero and **No** otherwise
**Prop**  If $𝐴×𝐵 = 𝐶$, then the algorithm always returns **Yes**. If $𝐴×𝐵 ≠ 𝐶$, then the probability it returns Yes is at most $\frac{1}{2}$.

## MAX-3-SAT

**Def**  <i><u>Boolean Variable</u></i>
A boolean variable is a variable that can take only the values True=$1$ or False=$0$.

**Def**  <i><u>Negation</u></i>
The negation/NOT operator of a boolean variable $𝑥$ is $\bar{𝑥} = 1 − 𝑥$.

**Def**  <i><u>Literal</u></i> and <i><u>Clause</u></i>
A literal is a boolean variable or its negation. A clause is a disjunction of literals.

**Def**  <i><u>Conjunctive Normal Form</u></i>
A boolean formula is in Conjunctive Normal Form (CNF) if it is the conjunction of several clauses. It is called a $i$CNF formula if all clauses contain $i$ literals.