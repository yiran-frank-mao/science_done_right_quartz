## Comparison-Based Algorithms

>[!definition] 
>**Def**  <i><u>In Place</u></i>
>A sorting algorithm is in place if the rearrangement of the elements happens inside the array: does not require additional memory, except some memory of constant size.

>[!definition] 
>**Def** <i><u> Stable</u></i>
>A sorting algorithm is stable if elements with the same values appear in the output array in the same order as they appear in the input array.

|                        | Insertion Sort           | Merge Sort      | RandQuick Sort |
| ---------------------- | ------------------------ | --------------- | -------------- |
| Time                   | Worst: $Θ(𝑛^2)$          |                 |                |
| Average: $\Theta(n^2)$ | Worst: $\Theta(n\log n)$ | Worst: $Θ(𝑛^2)$ |                |
| Average: $Θ(𝑛 \log n)$ |                          |                 |                |
| In Place               | Yes                      | No              | Yes            |
| Stable                 | Yes                      | Yes             | No             |

**Fact**  <i><u>Merge Sort vs RandQuick Sort</u></i>
- In practice, RandQuick Sort often performs close to average than worst case, and it is faster than Merge Sort.
- For problems where time guarantee is strict, Merge Sort would be better because even in the worst case, it is still in $O(𝑛 \log 𝑛)$.
- When memory is limited, RandQuick Sort would be better, as it is in place.
- When previous ordering matters, RandQuick Sort is problematic because it is unstable.

>[!theorem] 
>**Thrm**  <i><u>Comparison-Based Algorithms Theorem</u></i>
>Any comparison-based sorting algorithm requires $Ω(𝑛 \log 𝑛)$ comparisons in the worst case. Hence, its time complexity must be in $Ω(𝑛 \log 𝑛)$.
>**Proof**  Let’s first represent possible comparisons that might happen in sorting any permutation of $𝑛$ distinct numbers as a decision tree:
>![comparison-based-sorting|350](https://i.imgur.com/0hBq9Ga.png)
>In the worst case, the number of comparisons a comparison- based sorting algorithm performs would be the same as the number of levels in the tree.
>The decision tree has $𝑛!$ leaf nodes. A tree with $h$ levels has at most $2^h$ leaves. Thus
>$$ n!\leq2^{h} \Longrightarrow \log n!\leq h $$
>Since $\log 𝑛! = Ω(𝑛 \log 𝑛)$, we can get $h =Ω(𝑛 \log 𝑛)$.
>Therefore, any comparison-based sorting algorithm requires $Ω(𝑛 \log 𝑛)$ comparisons in the worst case.

## Counting Sort

>[!algorithm] 
>**Algorithm**  <i><u>Counting Sort</u></i>
>Counting Sort is designed for sorting integers from a small range. Assume we want to sort $𝐴 = [𝑎_1,𝑎_2,⋯,𝑎_n]$ when $𝑎_i$ is an integer between $0$ and $𝑀$. If $n$ is large but the range is small, there must be many elements with the same value. Counting sort uses this observation to sort the elements by counting elements of the same values.
>1. Construct a temporary array $𝐶$ of size $𝑀 + 1$, where the indices of $𝐶$ are the values of the input array and $𝐶[𝑖]$ is the number of times the value $𝑖$ appears in the input array.
>2. Use $𝐶$ to identify the right position for each element of the input array.
>3. Define array $𝑆$ of size $𝑀 + 1$, where $𝑆[𝑖]$ is the number of elements equal or smaller than $𝑖$ in $𝐴$.
>4. Output $𝑂$ by assigning values of $𝐴$ at index based on values of $𝑆$ and update $𝑆$, starting from last element of $𝐴$.
>```cpp
>CoutingSort(A)
>
>M <- the max value in A
>C = new Array(M+1)
>for j = 1 to n
>	C[A[j]]++
>
>S = new Array(M+1)
>S[0] = C[0]
>for i = 1 to M
>	S[i] = S[i-1] + C[i]
>
>O = new Array(n-1)
>for j = n to 1
>	O[S[A[j]]] = A[j]
>	S[A[j]]--
>
>return O
>```

>[!proposition] 
>**Prop**  Counting sort is not in place, but is stable.

>[!proposition] 
>**Prop**  The time complexity of counting sort is in $\Theta(n+M)$ where $n$ is the input size and the input ranges from $0$ to $M$. Since Counting Sort is often used for problems where $𝑀$ is much smaller than $𝑛$, the complexity is often stated as $Θ(n)$. However, if Counting Sort is applied to problems where the range of numbers is much larger than 𝑛, then the complexity is $Θ(𝑀)$.

## Bucket Sort

**Algorithm**  <i><u>Bucket Sort</u></i>
Bucket sort is mainly for sorting numbers in the interval $[0,1)$ that are drawn independently from a uniform distribution.The idea is to assign similar elements to the same bucket, and then sort elements within each bucket.
![bucket-sort|400](https://i.imgur.com/NQJx3pq.png)
```cpp
BucketSort(A)
n = A.length
B[1,...,n] <- array of empty linkedlist
for i = 1 to n
	insert A[i] into list B[floor(nA[i])]
for i = 1 to n
	sort linkedlist B[i]
concatenate lists B[i] in order
```

**Prop**  The average time complexity of bucket sort is in $O(n)$.
**Proof**

**Prop** Bucket sort is not in place but stable.

## Radix Sort

**Algorithm**  <i><u>Radix Sort</u></i>
The idea is to use a stable sort to sort the elements from the least to the most significant digit one by one.
```cpp
RadixSort(A)
d <- maximum number of digits in a number in A
for i = 1 to d
	stableSort(A) on digit i
```
Usually, Counting Sort is used inside the loop. The time complexity is in $Θ(𝑑𝑛)$, assuming Counting Sort is used.

**Prop**  RadixSort is not in place, but stable.

## Other Useful Resources
- [Timo Bingmann, 15 Sorting Algorithms in 6 Minutes](https://www.youtube.com/watch?v=kPRA0W1kECg)