## Probability Density Function

>[!theorem] Transformation of PDF
>Call $𝑓(𝑥)$ the probability distribution function of the random variable $𝑋$. For a transformation of the form $𝑦=𝑦(𝑥)$, we have the following holds:$$f(x)\dd x = f(y) \dd y.$$In other words, $$f(y)=f(x)\left|\frac{\dd x}{\dd y}\right|$$

<b><u>e.g.</u></b>  Suppose $𝑋∼𝑢(0,1)$. For $𝑦=𝑒^𝑥$, we have $𝑥=\ln𝑦$ and then $\dd x / \dd y=1/𝑦$. Moreover $𝑓(𝑥)=1$, then the result is $𝑓(𝑦)=1/𝑦$.

## Cumulative Distribution Function

**Def**  <i><u>Cumulative Distribution Function</u></i>
The cumulative distribution function (cdf) $F_{X}:\R \to [0,1]$ of a real random variable $X$, evaluated at $x$, is the probability that $X$ will take a value less than or equal to $x$:$$F_X(x)=\Pr(X\leq x)$$

**Prop**  
- $F_{X}$ is right-continuous monotone increasing
- $\lim_{x\to-\infty}F_{X}(x)=0$ and $\lim_{x\to\infty}F_{X}(x)=1$
**Proof**

**Prop**  Clearly by definition of cumulative distribution function, we have $$\pr(a<X\leq b)=F_X(b)-F_X(a)$$

**Prop**  The probability density function of a continuous random variable can be determined from the cumulative distribution function by differentiating: $$f_{X}(x)=\frac{\dd F_{X}(x)}{\dd x}$$

## Expected Value

> [!definition] Expected Value
> Let $(\Omega, \mathcal{F}, P)$ be a [[Random Variable and Probability Space#^c9205a|probability space]], and $X\colon \Omega \to \R$ be a measurable real-valued random variable. The *expected value* of $X$, denoted $\newcommand{\E}{\mathbb{E}}\E[X]$, is defined as the [[Integration on Measure Spaces#^56d25a|Lebesgue integral]] of $X$ with respect to the probability measure $P$:
> $$\E[X]:= \int_{\Omega} X \dd P.$$

^2f930b

