---
created: 2024-09-17
updated: 2024-10-21
completed: true
tags:
  - coding
---
## Interval Coding

> [!definition] Modified Cumulative Distribution Function
> Given a discrete probability distribution $\{ p_{i} \}$, we define the modified cumulative distribution function as: $$\bar{F}_{i}=\sum_{j=1}^{i-1}p_{j} + \frac12 p_{i}=F_{i}-\frac12 p_{i}$$where $F_{i}=\sum_{j=1}^{i} p_{j}$ is the usual cumulative distribution function.

> [!algorithm] Shannon-Fano-Elias Coding
> For each outcome $a_{i}$,
> 1. Calculate the value of modified cumulative distribution function $\bar{F}_{i}$.
> 2. Calculate the length of the required binary string $\ell(a_i)=\left\lceil\log_2\frac1{p_i}\right\rceil+1$.
> 3. Convert the value to binary $[\bar{F}_{i}]_{2}$.
> 4. Trim the binary string to the required length $\ell(a_i)$, assign the trimmed binary string to the outcome $a_{i}$ as its codeword.
> $\quad$

<u><b>e.g.</b></u>  Suppose $X$ has outcomes $(a_{1},a_{2}, a_{3},a_{4})$ and probabilities $\left(\frac29, \frac19, \frac13, \frac13 \right)$. Then we have the following table:

$x$ | $p(x)$ | $F(x)$ | $\bar{F}(x)$ | $[\bar{F}(x)]_2$ | $\ell(x)$|
---|---|---|---|---|---|
$a_{1}$ | $\frac29$ | $\frac29$ | $\frac19$| $0.\overline{000111}$| 4|
$a_{2}$ | $\frac19$ | $\frac13$ | $\frac{5}{18}$| $0.01\overline{000111}$| 5|
$a_{3}$ | $\frac13$ | $\frac23$ | $\frac{1}{2}$ | $0.1$| 3|
$a_{4}$ | $\frac13$ | $1$ | $\frac{5}{6}$ | $0.1\overline{10}$| 3|

Therefore we have the code $C=\{0001, 01000, 100, 110\}$.

## Lossless Property

> [!proposition]
> The Shannon-Fano-Elias code is [[Coding and Compression#^7df20a|lossless]].

*Proof*  Denote the Shannon-Fano-Elias code as $\lfloor\bar{F}_{i}\rfloor_{\ell_{i}}$ for the $i$th outcome $x_{i}\in X$. Then we have $$F_{i-1}<\lfloor\bar{F}_{i}\rfloor_{\ell_{i}}<F_{i}$$That is the codeword lies entirely in the interval between $i−1$ and $i$, and these intervals are disjoint. Therefore, the code is lossless. $\square$

## Prefix Property

> [!proposition]
> Shannon-Fano-Elias code is [[Shannon Coding#^d751a1|prefix free]].

*Proof*  According to the previous argument, we know that $\lfloor\overline{F}_{i}\rfloor_{\ell_{i}}>F_{i-1}$. Additionally, $$\lfloor\bar{F}_{i}\rfloor_{\ell_{i}}+\frac{1}{2^{\ell}}\leq\bar{F}_{i}+\frac{1}{2^{\ell}} \leq \bar{F}_{i} + \frac{p_{i}}{2}=F_{i}$$Hence $$\left[\lfloor\bar{F}_{i}\rfloor_{\ell_{i}},\lfloor\bar{F}_{i}\rfloor_{\ell_{i}}+\frac{1}{2^{\ell}}\right)\subset[F_{i-1},F_{i})$$The intervals for each codeword are thus trivially disjoint, since we know each of the $[F_{i-1} F_{i})$ interval is disjoint, thus the code is prefix free. $\square$

## Shannon-Fano-Elias Decoding

> [!algorithm] Shannon-Fano-Elias Decoding
> To decode a given bitstring,
> 1. start with the first bit, compute the corresponding binary interval;
> 2. if the interval is strictly contained within that of a codeword:
> 	1. output the corresponding outcome
> 	2. skip over any redundant bits for this codeword
> 	3. repeat the process with the remaining bits
> 3. otherwise include next bit and compute the corresponding interval.
>

<u><b>e.g.</b></u>  Suppose we have $\mathcal{A}=(\text{a}_{1}, \text{a}_{2}, \text{a}_{3}, \text{a}_4)$ with $p=\left(\frac29, \frac19, \frac13, \frac13\right)$ and we want to decode $01000$:
![shannon_fano_elias_decoding.jpeg|450](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/shannon_fano_elias_decoding.jpeg)
We could actually stop the process once we see $0100$ since $[0.25,0.3125)\subset[0.22,0.33]$.

## Expected Length

> [!theorem]
> The expected length of a Shannon-Fano-Elias code $C$ on ensemble $X$ satisfies: $$H(X)+1\leq L(C,X)\leq H(X)+2.$$

*Proof*  $$L(C,X)=\sum_{i=1}^{n}p_i\ell(a_i)=\sum_{i=1}^{n}p_i\left(\left\lceil\log_2\frac1{p_i}\right\rceil+1\right)\leq\sum_{i=1}^{n}p_i\left(\log_2\frac1{p_i}+2\right)=H(X)+2$$The lower bound is similarly obtained.
