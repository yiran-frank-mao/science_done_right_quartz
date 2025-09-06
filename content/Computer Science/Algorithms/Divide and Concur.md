**Prob**  <i><u>Closest Pairs of Points</u></i>
Given a set of points $𝑃 = \{ (𝑥_1,𝑦_1) ,\dots, (𝑥_n,𝑦_n) \}$ in the two- dimensional plane, find a pair of points in $𝑃$, such that the Euclidean distance is smallest.
![Divide-concur-1|400](https://i.imgur.com/mlrHjsl.png)

**Algorithm**  <i><u>Divide and Concur Algorithm</u></i>
The idea is to continue dividing the problem into two sub-problems of “almost” the same size until the problems are of size 3 and smaller.
1. We start by sorting the points in $𝑃$ by $𝑥$-coordinate and $𝑦$-coordinate and store these orderings in arrays $𝑋$ and $𝑌$.
2. We find a vertical line $𝐿$ which divides the points into two subset of almost equal size. Note that this can be done using the ordered array $𝑋$ based on the $𝑥$-coordinate.![dc2|350](https://i.imgur.com/Ost2zHN.png)
3. Suppose $𝑑_l$ is the distance of the closest pair in the left point set and $𝑑_r$ is for the right point set, then $𝑑 \leq \min(𝑑_l , 𝑑_r)$. Then, we want to check if there is a point on the left and a point on the right with a smaller distance than $𝑑$. ![dc3|400](https://i.imgur.com/uSPbVQy.png)
4. Suppose we are processing the point with the black arrow (moving from bottom to top). We only need to consider points whose $𝑦$-coordinate is less than its $𝑦$-coordinate plus $𝑑$. ![dc4|350](https://i.imgur.com/j33dSXm.png)

**Prop** The time complexity of the above example is in $O(n \log n)$.