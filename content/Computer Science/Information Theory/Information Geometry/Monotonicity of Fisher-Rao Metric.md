---
created: 2024-10-09
updated: 2024-10-10
---
> [!definition] Stochastic Map
A stochastic map is a linear map $T$ from the space of probability measures on some set $A$ to the space of probability measures on some set $B$. Explicitly, we require$$T\colon P(A)\to P(B)\quad  \mu \mapsto \sum_{a\in A} \mu(a) \cdot T(\delta_{a})$$where $\delta_{a}$ is the point measure at $a$.

> [!theorem]
> The relative entropy $S$ is monotone. i.e. for any stochastic map $T\colon P(X)\to P(Y)$, we have $$S(Tp:Tq)\leq S(p:q)$$

*Proof*  $$\begin{aligned}S(Tp:Tq)&= \sum_{y\in Y} (Tp)(y) \log \frac{(Tp)(y)}{(Tq)(y)} \\ &= \sum_{y\in Y} \left(\sum_{x\in X} p(x) (T\delta_{x})(y)\right) \log \frac{\sum_{x\in X} p(x) (T\delta_{x})(y)}{\sum_{x\in X} q(x) (T\delta_{x})(y)}\\&=\sum_{y\in Y} \left(\sum_{x\in X} p(x) (T\delta_{x})(y)\right) \log \frac{\sum_{x\in X} p(x) (T\delta_{x})(y)}{\sum_{x\in X} p(x) \frac{q(x)}{p(x)} (T\delta_{x})(y)}\end{aligned}$$By [[Information Content and Entropy#^00c508|joint convexity of relative entropy]], we have $$\begin{aligned}&\sum_{y\in Y} \left(\sum_{x\in X} p(x) (T\delta_{x})(y)\right) \log \frac{\sum_{x\in X} p(x) (T\delta_{x})(y)}{\sum_{x\in X} p(x) \frac{q(x)}{p(x)} (T\delta_{x})(y)}\\ \leq& \sum_{x\in X} p(x) \left(\sum_{y\in Y} (T\delta_{x})(y)\log\frac{(T\delta_{x})(y)}{\frac{q(x)}{p(x)}\cdot (T\delta_{x})(y)}\right)\\=& \sum_{x\in X} p(x) \left( \sum_{y\in Y} (T\delta_{x})(y)\log \frac{p(x)}{q(x)}\right) \\=& \sum_{x\in X} p(x) \log\frac{p(x)}{q(x)}\\=&S(p:q)\end{aligned}$$which is the desired result. $\square$
