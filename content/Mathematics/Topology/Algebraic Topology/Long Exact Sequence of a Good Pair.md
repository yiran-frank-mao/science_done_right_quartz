> [!theorem] Long Exact Sequence of a Good Pair
> For a good pair $(X, A)$, there is a long exact sequence in homology:
> $$\cdots \to H_n(A) \xrightarrow{i_*} H_n(X) \xrightarrow{j_*} \tilde{H}_n(X/A) \xrightarrow{\partial} H_{n-1}(A) \xrightarrow{i_{*}} \cdots$$
> The maps are:
> - $i_*$: induced by the inclusion map $i\colon A \hookrightarrow X$.
> - $j_*$: induced by the quotient map $j\colon X \to X/A$.
> - $\partial$: the boundary map.
>   
> Optionally, we can write the sequence in reduced homology as:
> $$\cdots \to \tilde{H}_n(A) \xrightarrow{i_*} \tilde{H}_n(X) \xrightarrow{j_*} \tilde{H}_n(X/A) \xrightarrow{\partial} \tilde{H}_{n-1}(A) \xrightarrow{i_{*}} \cdots$$
> But note that $\tilde{H}_n(X/A)$ is **always** reduced. ^a8a98c

*Proof*  This can be concluded from 

## Applications

> [!corollary]
> The reduced homology of the n-sphere $S^n$ is given by:
> $$\tilde{H}_k(S^n) \cong \begin{cases} \Z & k=n \\ 0 & k \neq n \end{cases}$$

*Proof*  We will prove by induction on $n$.
**Base Case (n=0):** $S^0$ consists of two points, $\{-1, 1\}$. $H_0(S^0) \cong \Z \oplus \Z$. The reduced homology is $\tilde{H}_0(S^0) \cong \Z$ and $\tilde{H}_k(S^0) = 0$ for $k > 0$. The formula holds.
**Inductive Step:** Assume the formula holds for $n-1$. Consider the good pair $(D^n, S^{n-1})$. The quotient space $D^n/S^{n-1}$ is homeomorphic to $S^n$. The long exact sequence in reduced homology is: $$\cdots \to \tilde{H}_k(D^n) \to \tilde{H}_k(S^n) \xrightarrow{\partial} \tilde{H}_{k-1}(S^{n-1}) \to \tilde{H}_{k-1}(D^n) \to \cdots.$$Since the disk $D^n$ is contractible, its reduced homology groups are all zero: $\tilde{H}_k(D^n) = 0$ for all $k$. The sequence simplifies to: $$\cdots \to 0 \to \tilde{H}_k(S^n) \xrightarrow{\partial} \tilde{H}_{k-1}(S^{n-1}) \to 0 \to \cdots.$$Exactness implies that the connecting homomorphism $\partial\colon \tilde{H}_k(S^n) \to \tilde{H}_{k-1}(S^{n-1})$ is an isomorphism for all $k$. By the inductive hypothesis, $\tilde{H}_{k-1}(S^{n-1})$ is $\Z$ for $k-1 = n-1$ (i.e., $k=n$) and $0$ otherwise. Therefore, the same is true for $\tilde{H}_k(S^n)$, completing the induction. $\square$

The long exact sequence can be used to prove Brouwer's fixed point theorem for higher dimensions:

> [!theorem] Brouwer's Fixed Point Theorem
> Any continuous map $f\colon D^n \to D^n$ has a fixed point.

*Proof*  Assume there exists a map $f\colon D^n \to D^n$ with no fixed points. We can then define a retraction $r\colon D^n \to \partial D^n = S^{n-1}$ by sending a point $x$ to the intersection of the ray from $f(x)$ through $x$ with the boundary sphere $S^{n-1}$ (just like what we did [[The Fundamental Group#^01b5b9|here]]).
Let $i\colon S^{n-1} \hookrightarrow D^n$ be the inclusion map. The composition $r \circ i\colon S^{n-1} \to S^{n-1}$ is the identity map. Note that $(S^{n},S^{n-1})$ is a good pair, so $$\tilde{H}_{n-1}(S^{n-1}) \xrightarrow{i_*} \tilde{H}_{n-1}(D^n) \xrightarrow{r_*} \tilde{H}_{n-1}(S^{n-1})$$is an exact sequence. However, $\tilde{H}_{n-1}(S^{n-1})\cong \Z$, $\tilde{H}_{n-1}(D^{n})\cong 0$ and $\tilde{H}_{n-1}(S^{n-1})\cong \Z$, so it is impossible to compose to the identity, yielding a contradiction. $\square$ 