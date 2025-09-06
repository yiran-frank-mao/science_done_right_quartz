---
updated: 2024-10-14
created: 2024-01-30
completed: true
---
## Entropy

> [!definition] Ensemble
> An ensemble $\newcommand{\dd}{\:\mathrm{d}} X$ is a triple $(x , \mathcal{A}_{X} , \mathcal{P}_{X})$ where $x$ is a random variable taking values in $\mathcal{A}_{X} = \{a_{1},a_{2},\dots,a_{I}\}$ with probabilities $\mathcal{P}_{X} = \{p_{1},p_{2},\dots,p_{I}\}$.

> [!definition] Information Content
> Information content of an outcome $x\in X$ with probability $p(x)$ is defined as $$h(x) = \log \frac{1}{p(x)} = - \log p(x)$$

>[!warning]+
>The choice of logarithm basis is arbitrary. Normally we use $2$ and measure information in bits. All following contents will restrict on base $2$.

>[!definition] Shannon Entropy
> Entropy of a random variable is defined as average information content: $$H(X) =\sum_{x \in X} -p(x)\log p(x)=\int-\pi(x)\log\pi(x)\dd x$$ ^d1821a

>[!remark]+
>Entropy describes the uncertainty of a random variable.

>[!proposition]
>Entropy has the following properties:
> - $H\left( x\right) \geq 0$.
> - For the distribution function, more sharply, lower entropy, more evenly, higher entropy.
> - $H\left( x\right) \leq \log(N)$ with equality if and only if $x \sim u(N)$.
> - Entropy is the lower bound on the average number of  bits to transmit the state of a random variable.
> - The number of binary questions lies between $H(x)$ and $H(x)+1$.
> $\quad$

>[!theorem]
>Consider a discrete variable $X$ taking on values from the finite set $\chi$ . Let $p_{i}$ be the probability of each state, with $i=1,\dots,N$. Denote the vector of probabilities with $\vec{p}$. Then the entropy is maximized if $\vec{p}$ is uniform. That is $$H(X)\leq \log N$$with equality iff $p_{i}=\frac{1}{N}$ for all $i$.

*Proof*  The object function is $H(X)=-\sum_{i=1}^{N}p_{i}\log p_{i}$ subject to the constraint $\sum_{i=1}^{N}p_{i}=1$. By [[Lagrangian and Lagrange Dual#^bf5e08|strong duality]], we optimize its [[Lagrangian and Lagrange Dual#^f694a1|Lagrange dual problem]]: $$\mathcal{L}=-\sum_{i=1}^{N}p_{i}\log p_{i}+\lambda \left(\sum_{i}p_{i}-1\right)$$It follows that $$\begin{aligned}
\frac{\partial\mathcal{L}}{\partial\lambda} \sum_{i}p_{i}-1 =0 \\ \frac{\partial\mathcal{L}}{\partial{p_{j}}}=-(\log p_{j}+1)+\lambda = 0
\end{aligned}$$Sum over all of the $p_{j}$, obtaining: $$\sum_{j=1}^{N}p_{j}=\sum_{j=1}^{N}2^{\lambda-1}$$Therefore $\lambda = 1 - \log N$. Hence $\log p_{j} = 1-\log N -1= -\log N$, i.e. $p_{j}= \frac{1}{N}$ for all $j$.

>[!proposition]
>Entropy is a lower bound on the average number of bits to transmit the state of a random variable. That is the number of binary questions to describe the information lies between $H(X)$ and $H(X)+1$.

## Joint and Conditional Entropy

>[!definition] Conditional Entropy
The conditional entropy describes average uncertainty that remains about $X$ when $Y$ is known: $$\begin{aligned} H(X \mid Y) &=\sum_y p(y)H(X|Y=y)\\&=\sum_y p(y) \sum_x p(x \mid y) \log \frac{1}{p(x \mid y)} \\&= \sum_x \sum_y p(x,y)\log \frac{1}{p(x \mid y)}\end{aligned}$$

>[!definition] Joint Entropy
The joint uncertainty of $X$ and $Y$ is the uncertainty of $X$ plus the uncertainty of $Y$ given $X$:$$H(X, Y) =\sum_{x, y} p(x, y) \log \frac{1}{p(x, y)}= H(X) + H(Y \mid X) = H(Y) + H(X \mid Y)$$

## Relative Entropy and Mutual Information

>[!definition] Relative Entropy (KL Divergence)
> The relative entropy or KL divergence given probability distributions $p$ and $q$ is defined as$$D_{\mathrm{KL}}(p \| q)=\sum_x p(x) \log \frac{p(x)}{q(x)}$$ ^b73be4

>[!proposition]
>The KL divergence has the following properties:
> - $D_{\mathrm{KL}}(p \| q) \geq 0$ with equality if and only if $p=q$.
> - Not symmetric: $D_{\mathrm{KL}}(p \| q) \neq D_{\mathrm{KL}}(q \| p)$.
> - Not satisfy triangular inequality.
> $\quad$

>[!proposition]
> Relative entropy is jointly convex. That is for any $\lambda \in[0,1]$, we have:$$D_{\mathrm{KL}}\left(\lambda p_{1}+(1-\lambda)p_{2} \| \lambda q_{1}+(1-\lambda)q_{2}\right)\leq \lambda D_{\mathrm{KL}}(p_{1} \| q_{1})+(1-\lambda)D_{\mathrm{KL}}(p_{2} \| q_{2})$$^00c508

*Proof*  It suffices to show that for any $i\in X$, $$\begin{aligned}(\lambda p_1(i)+(1-\lambda) p_{2}(i)) \log \frac{\lambda p_1(i)+(1-\lambda) p_{2}(i)}{\lambda q_1(i)+(1-\lambda) q_{2}(i)} \\ \leq \lambda \left(p_{1}(i)\log \frac{p_{1}(i)}{q_{1}(i)}\right)+(1-\lambda)\left(p_{2}(i)\log \frac{p_{2}(i)}{q_{2}(i)}\right)\end{aligned}$$We can see this by checking convexity of $g\colon [0,1] \times  [0,1] \to \R, (x,y)\mapsto x\log \frac{x}{y}$. The Hessian of $g$ is given by $$\nabla^{2}g=\begin{pmatrix} \frac{1}{x} & -\frac{1}{y} \\ -\frac{1}{y} & \frac{x}{y^{2}} \end{pmatrix}= \frac{1}{y} \begin{pmatrix}\frac{y}{x} & -1 \\ -1 & \frac{x}{y}\end{pmatrix} $$which is positive semidefinite, hence $g$ is convex. $\square$

>[!definition] Mutual Information
> The mutual information of two random variable $X$ and $Y$ is defined as:$$I(X ; Y) =D_{\mathrm{KL}}(p(X, Y) \| p(X) p(Y)) =\sum_{x \in \mathcal{X}} \sum_{y \in \mathcal{Y}} p(x, y) \log \frac{p(x, y)}{p(x) p(y)}$$

>[!proposition]
>The mutual information has the following properties:
> - $I(X ; Y)=H(X)-H(X \mid Y)=H(Y)-H(Y \mid X)$.
> - $I(X ; Y) \geq 0$ with equality if and only if $X \perp Y$.
> - $I(X ; Y) = I(Y ; X)$.
> - $I(X ; X) = H(X)$.
>
> ![entropy|400](https://i.imgur.com/HVFq4fh.png)
