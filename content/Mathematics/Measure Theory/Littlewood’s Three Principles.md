We may summarize the properties of measurable sets and measurable functions by the following three principles, which give an intuitive understanding.

> [!principle] Littlewood’s Three Principles
> The following principles hold:
> 1. Every (measurable) set is nearly a finite union of intervals.
> 2. Every (measurable) function is nearly continuous.
> 3. Every convergent sequence is nearly uniformly convergent.
>$\quad$

A precise description of the third principle is given by the Egorov's theorem:

> [!theorem] Egorov's Theorem
> Suppose $\{f_{k}\}_{k=1}^{\infty}$ is a sequence of measurable functions defined on a measurable set $E$ with $m(E)<\infty$, and assume that $f_{k}\to f$ pointwisely a.e. on $E$. Given $\varepsilon>0$, we can find a closed set $A_{\varepsilon}\subset E$ such that $m(E\setminus A_{\varepsilon})\leq\varepsilon$ and $f_{k}\to f$ uniformly on $A_{\varepsilon}$. ^4b1ce2

> [!theorem] Lusin's Theorem
> Suppose $f$ is measurable and finite valued on $E$ with $m_{*}(E)<\infty$. Given $\varepsilon>0$, we can find a closed set $A_{\varepsilon}\subset E$ such that $m_{*}(E\setminus A_{\varepsilon})\leq\varepsilon$ and $f$ is continuous on $A_{\varepsilon}$.

*Proof*  By [[Lebesgue Measurable Functions#^d54652|the theorem]], let $f_{n}$ be a sequence of step functions so that $f_{n}\to f$ a.e. Then we can find sets $E_{n}$ so that $m_{*}(E_{n})<\frac{1}{2^{n}}$ and $f_{n}$ is continuous outside $E_{n}$

Although there exist Lebesgue measurable sets that are not Borel sets, you are unlikely to encounter one. Similarly, a Lebesgue measurable function that is not Borel measurable is unlikely to arise in anything you do.