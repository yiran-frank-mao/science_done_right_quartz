---
created: 2024-07-19
updated: 2024-09-21
---
> [!definition] Uniquely Decodable Code
> A code $\newcommand{\N}{\mathbb{N}}c$ for $X$ is uniquely decodable if no two strings from $\mathcal{A}^+_{X}$ have the same codeword. That is, for all $x,y \in \mathcal{A}^+_{X}$, $$x\neq y \implies c(x)\neq c(y).$$

<u><b>e.g.</b></u>  $c \colon \text{a}\mapsto 1, \text{b} \mapsto 10, \text{c} \mapsto 110, \text{d} \mapsto 111$ is not uniquely decodable since $c(\text{aaa})=c(d)=111$.

> [!proposition]
> Uniform lossless codes are uniquely decodable; Uniquely decodable codes are lossless.

*Proof*  Let $c$ be a uniform lossless code. Then $c$ is injective. So for all $x,y \in \mathcal{A}_{X}^+$ such that $x \neq y$, there is some $n\in\N$, that the $n$th characters $x_{n} \neq y_{n}$. By injectivity of $c$, $c(x_{n})\neq c(y_{n })$. Since $c$ is uniform, $c(x)\neq c(y)$, $c$ is uniquely decodable.  $\square$

> [!definition] Prefix Codeword
> A codeword $\mathbf{c}\in \{0,1\}^{+}$ is said to be a prefix of another codeword $\mathbf{c}^{\prime} \in \{0,1\}^+$ if there exists a string $\mathbf{ t}\in \{0,1\}^{+}$ such that $\mathbf{c}^{\prime}=\mathbf{c}\mathbf{t}$.

<u><b>e.g.</b></u>  $\text{01101}$ has prefix $\text{011}$.

> [!definition] Prefix Free Code
> A code $c$ with range $C=\{\mathbf{c}_{1},\dots,\mathbf{c}_{l}\}$ is a prefix (free) code if no codeword is a prefix of another codeword. That is, for all $\mathbf{c}_{i}\in C$ there is no prefix of $\mathbf{c}_{i}$ in $C$.

<u><b>e.g.</b></u>  $\text{a}\mapsto 0, \text{b}\mapsto 10, \text{c}\mapsto 110, \text{d}\mapsto 111$ is a prefix code. ^d751a1

> [!proposition]
> Prefix codes are uniquely decodable, but not vice versa.

<u><b>e.g.</b></u>  The code $C=\{0,01,011\}$ is uniquely decodable but not a prefix code.

>[!theorem] The Kraft-McMillan Inequality
>For any uniquely decodable binary code $c$, its codeword length $\{l_{1}, \dots, l_{n}\}$ satisfy $$\sum_{i=1}^{n}2^{-l_{i}}\leq 1$$Conversely, if the set $\{ l_{1},\dots,l_{n} \}$ satisfy the above inequality, then there exists a uniquely decodable code $c$ with codeword lengths $\{ l_{1},\dots,l_{n} \}$.

<u><b>e.g.</b></u>  $C=\{0001, 0010, 0100, 1000\}$ is prefix and $\sum^{4}_{i=1}2^{-4}=\frac{1}{4} \leq 1$. ^263caf

## Expected Code Length and Shannon Coding

> [!definition] Expected Code Length
> The expected length for a code $c$ of an ensemble $X$ is given by $$L(c,X)=\sum_{x\in \mathcal{A}_{X}}P(x)l(x)$$where $l(x)$ is the length of the codeword for $x$.

> [!definition] Probabilities From Code Lengths
> Given a code $c$ for $X$ with lengths $l=\{l_{1},\dots,l_{n}\}$, such that $\sum_{i=1}^{n} 2^{-l_{i}}\leq 1$, we define $\mathbf{q}=(q_{1},\dots q_{n})$, the probability vector for $l$, by $$q_{i}=\frac{2^{-l_{i}}}{\sum_{i=1}^{n} 2^{-l_{i}}}$$

The goal of compression is to answer the question that, given an ensemble $X$ with probabilities $p = \{p_{1}, \dots , p_{n} \}$ how can we minimise the expected code length?

> [!proposition] Limits of Compression
> Given an ensemble $X$ with probabilities $\mathbf{p}$, and prefix code $c$ with codeword length probabilities $\mathbf{q}$ and normalisation $z=\sum_{i=1}^{n} 2^{-l_{i}}$. Then $$L(c, X)=H(X)+D_{\text{KL}}(\mathbf{p}\|\mathbf{q})+\log_{2}\frac{1}{z}\geq H(X)$$with equality only when $l_{i}=\log_{2}\frac{1}{p_{i}}$. Here $D_{\text{KL}}(\mathbf{p}\|\mathbf{q})$ is the [[Information Content and Entropy#^b73be4|KL divergence]].

**Proof**  

> [!definition] Shannon Code
> Given a finite ensemble $X$ with probabilities $p_{1},\dots, p_n$. A code $C$ is called a Shannon code for $X$ if it has code lengths $l$ such that $$\ell_i=\left\lceil\log_2\frac1{p_i}\right\rceil\geq\log_2\frac1{p_i}.$$

<u><b>e.g.</b></u>  If $p=(0.5, 0.25,0.25)$, then $C=(0,10,11)$ with $\ell=(1,2,2)$ is a Shannon code.

> [!theorem] Shannon Coding Theorem for Symbol Codes
> For any ensemble $X$, there exists a prefix code $C$ such that $$H(X)\leq L(C,X) < H(X) +1$$In particular, any Shannon code $C$ has expected code length within $1$ bit of the entropy.
> **Proof**  Clearly for any real $x$ we have $x\leq\lceil x\rceil<x+1$. Therefore, if we create a Shannon code $C$ for some ensemble $X$ with $\mathbf{p}=(p_{1},\dots, p_{n})$, it satisfies $$\ell_i=\left\lceil\log_2\frac1{p_i}\right\rceil<\log_2\frac1{p_i}+1$$Thus $$\begin{aligned}
L(C,X)&=\sum_{i} p_{i} \ell_{i} \\ &< \sum_{i} p_{i} \left(\log_{2}\frac{1}{p_{i}}+1\right) \\ &=\sum_{i} p_{i}\log_{2}\frac{1}{p_{i}} + \sum_{i} p_{i} \\ &=  H(X) +1
\end{aligned}$$Since $\ell_i=\left\lceil\log_2\frac1{p_i}\right\rceil \geq -\log_{2} p_{i}$ we have $2^{-\ell_i}\leq2^{\log_2p_i}=p_i$, it follows that $\sum_i2^{-\ell_i}\leq\sum_ip_i=1$, so there is a prefix code with length $\ell$ by the [[Shannon Coding#^263caf|Kraft-McMillan inequality]].

>[!remark]
>The Shannon coding theorem for symbol codes is just exactly the source coding theorem for symbol codes.

>[!proposition] 
> Shannon codes do not necessarily have smallest expected length.

*Proof*  Consider $p_{1}= 0.0001$ and $p_{2}=0.9999$. Notice that $H(X)=0.0013$. Then the Shannon code $C$ has $\ell_{1}=14$ and $\ell_{2}=1$ so the expected length is $1.0013$. However, the code $C^{\prime}=(0,1)$ with $\ell_{1}=1$ and $\ell_{2}=1$ has expected length $1$. $\square$











