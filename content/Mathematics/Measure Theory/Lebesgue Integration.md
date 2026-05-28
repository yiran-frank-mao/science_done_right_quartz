## Integration of Simple Functions

> [!definition] Lebesgue Integral of a Simple Function  
> If $\varphi$ is a [[Lebesgue Measurable Functions#^ad60a2|simple function]] with canonical form $\newcommand{\dd}{\:\mathrm{d}}\newcommand{\ddf}[2]{\frac{\dd #1}{\dd #2}}\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}}\newcommand{\R}{\mathbb{R}}\varphi(x) = \sum_{k=1}^{N} c_k \chi_{F_k}(x),$ then the Lebesgue integral of $\varphi$ is defined as  
> $$\int_{\R^{d}} \varphi(x) \dd x = \sum_{k=1}^{N} c_k m(F_k).$$  
> If $E$ is a measurable subset of $\R^d$ with finite measure, then $\varphi(x) \chi_E(x)$ is also a simple function, and we define  
> $$\int_{E} \varphi(x) \dd x = \int \varphi(x) \chi_{E(x)} \dd x.$$ ^ebf616

<u><b>e.g.</b></u>  Integral of a characteristic function is the measure of the set.

> [!proposition] Properties of the Integral of Simple Functions  
> The integral of simple functions satisfies the following properties:  
> 1. **Independence of the representation**: If $\varphi = \sum_{k=1}^{N} a_k \chi_{E_k}$ is any representation of $\varphi$, then  
>    $$\int \varphi = \sum_{k=1}^{N} a_k m(E_k).$$  
> 2. **Linearity**: If $\varphi$ and $\psi$ are simple functions, and $a, b \in \R$, then  
>    $$\int (a\varphi + b\psi) = a \int \varphi + b \int \psi.$$  
> 3. **Additivity**: If $E$ and $F$ are disjoint subsets of $\R^d$ with finite measure, then  
>    $$\int_{E \cup F} \varphi = \int_E \varphi + \int_F \varphi.$$  
> 4. **Monotonicity**: If $\varphi \leq \psi$ are simple functions, then  
>    $$\int \varphi \leq \int \psi.$$  
> 5. **Triangle inequality**: If $\varphi$ is a simple function, then so is $|\varphi|$, and  
>    $$\left| \int \varphi \right| \leq \int |\varphi|.$$
>
>$\quad$

> [!proposition] 
> If $f$ and $g$ are a pair of simple functions that agree almost everywhere, then  
> $$\int f = \int g.$$  
> This identity of integrals for functions that agree almost everywhere will continue to hold for successive definitions of the integral.

## Bounded Functions Supported on a Set of Finite Measure

> [!definition]  Support
> Suppose that $f:X\to\R$ is a real valued function whose domain is an arbitrary set $X$. The support of $f$, written $\newcommand{\supp}{\operatorname{\mathrm{supp}}}\supp(f)$, is the set of points in $X$ where $f(x)$ is non-zero:$$\supp(f)=\{x\in X\mid f(x)\neq0\}$$If $f(x)=0$ for all but a finite number of points in $X$, then $f$ is said to have finite support. We shall also say that $f$ is supported on a set $E$, if $f (x) = 0$ whenever $x \notin E$. ^7e0caa

 > [!proposition]
 > If $f$ is measurable then $\supp(f)$ is a measurable set.

> [!proposition]
> If $f$ is a measurable function bounded by $M$ and supported on a set $E$, then there exists a sequence $\{\phi_{n}\}$ of simple functions, with each $\phi_{n}$ bounded by $M$ and supported on $E$, and such that $$\phi_{n}(x)\to f(x),\quad \text{for all } x.$$

*Proof*  Since $f$ is bounded by $M$, $f+M$ is a non-negative function. [[Lebesgue Measurable Functions#^ac3203|The theorem]] states that there exists an increasing sequence of non-negative simple functions $\{\varphi_{n}\}$ converging pointwise to $f+M$. Define $\phi_{n}:=\varphi_{n}-M$. Then $\phi_{n}$ is a sequence of simple functions bounded by $M$ and converging pointwise to $f$. $\square$

The following lemma allows us to define the integral for bounded functions supported on sets of finite measure:

> [!lemma] 
> Let $f$ be a bounded function supported on a set $E$ of finite measure. If $\{\varphi_n\}_{n=1}^{\infty}$ is any sequence of simple functions bounded by $M$, supported on $E$, and with $\varphi_n(x) \to f(x)$ for a.e. $x$, then:  
> 1. The limit $\lim\limits_{n \to \infty} \int \varphi_n$ exists.  
> 2. If $f = 0$ a.e., then the limit $\lim\limits_{n \to \infty} \int \varphi_n$ equals $0$.
> $\quad$

> [!definition]  Lebesgue Integral of a Bounded Function Supported on Sets of Finite Measure
> Let $f$ be a measurable function bounded by $M$, supported on a set $E$ of finite measure. We define the Lebesgue integral of $f$ as  $$\int f :=\lim_{n\to \infty} \int \varphi_{n}$$ where $\{\varphi_{n}\}$ is a sequence of simple functions bounded by $M$, $\supp(\varphi_{n})\subseteq \supp(f)$, and converging pointwise to $f$ a.e.

> [!theorem] Bounded Convergence Theorem  
> Suppose that $\{f_n\}_{n=1}^{\infty}$ is a sequence of measurable functions that are all bounded by $M$, are supported on a set $E$ of finite measure, and $f_n(x) \to f(x)$ for a.e. $x$ as $n \to \infty$. Then $f$ is measurable, bounded, supported on $E$ for a.e. $x$, and  
> $$\int |f_n - f| \to 0 \quad \text{as } n \to \infty.$$  
> Consequently,  
> $$\int f_n \to \int f \quad \text{as } n \to \infty.$$ ^098e7e

*Proof*  Fix any $\varepsilon>0$, by [[Littlewood’s Three Principles#^4b1ce2|Egorov's theorem]], we can find a closed set $A_{\varepsilon}\subset E$ such that $m(E\setminus A_{\varepsilon})\leq\varepsilon$ and $f_{n}\to f$ [[Convergence of Functions#^a59a2d|uniformly]] on $A_{\varepsilon}$, so there exists $N$ such that $|f_{n}(x)-f(x)|\leq \varepsilon$ for all $n\geq N$ and $x\in A_{\varepsilon}$. Then we have $$\begin{aligned}\int |f_{n}-f|&\leq\int_{A_{\varepsilon}}|f_{n}-f|+\int_{E\setminus A_{\varepsilon}}|f_{n}-f|\\&\leq \varepsilon m(A_{\varepsilon})+2Mm(E\setminus A_{\varepsilon})\\&\leq(2M+m(E))\varepsilon\end{aligned}$$for all $n\geq N$. Since $\varepsilon$ is arbitrary, we have $\int |f_{n}-f|\to 0$. $\square$

> [!remark]
> The Bounded Convergence Theorem is about interchange of limits and integrals. It says, under certain conditions, we can interchange the limit and the integral: 
> $$\lim_{n\to\infty}\int f_n=\int\lim_{n\to\infty}f_n.$$

> [!proposition]
> If non-negative $f$ is bounded and supported on a set of finite measure $E$ and $\int f=0$, then $f=0$ a.e.

*Proof*  For each integer $n\geq 1$, we have $$f(x)\geq\frac{\chi_{\{f\geq 1/n\}\cap E}(x)}{n},$$this implies $$\int f \geq \frac{m\left(\{f\geq 1/n\}\cap E\right)}{n}$$by monotonicity. Thus $m\left(\{f\geq 1/n\}\cap E\right)=0$ for all $n$, and since $\{f>0\}=\bigcup_{n=1}^{\infty} \{f\geq 1/n\}\cap E$, we have $m(\{f>0\})=0$. $\square$

## Relationship with Riemann Integral

> [!theorem]
> Suppose $f$ is Riemann integrable on the closed interval $[a,b]$. Then $f$ is measurable, and  
> $$\int_{[a,b]}^{\mathcal{R}} f(x) \dd x = \int_{[a,b]}^{\mathcal{L}} f(x) \dd x,$$  
> where the integral on the left-hand side is the standard Riemann integral, and that on the right-hand side is the Lebesgue integral.

## Non-negative Measurable Functions

> [!definition] Extended Lebesgue Integral of a Non-negative Measurable Function
> Suppose $f$ is a non-negative measurable function, which is not necessarily bounded. We define the extended Lebesgue integral of $f$ as $$\int f = \sup_{0\leq g\leq f} \int g$$where the supremum is taken over all non-negative measurable functions $g$ that are bounded and supported on a set of finite measure.
> If the supremum is finite, then we say that $f$ is Lebesgue integrable. Clearly if $E$ is any measurable set, then we define $$\int_{E} f = \int f\chi_{E}$$

> [!proposition] Properties of the Integral of Non-Negative Measurable Functions  
> The integral of non-negative measurable functions enjoys the following properties:
> 1. **Linearity**: If $f, g \geq 0$, and $a, b$ are positive real numbers, then $\int (a f + b g) = a \int f + b \int g.$ 
> 2. **Additivity**: If $E$ and $F$ are disjoint subsets of $\R^d$, and $f \geq 0$, then $\int_{E \cup F} f = \int_E f + \int_F f.$ 
> 3. **Monotonicity**: If $0 \leq f \leq g$, then $\int f \leq \int g.$
> 4. **Triangle inequality**: If $f$ is a non-negative measurable function, then so is $|f|$, and $\left| \int f \right| \leq \int |f|.$
> 5. If $g$ is integrable and $0\leq f\leq g$, then $f$ is integrable.
> 6. If $f$ is integrable, then $f(x)<\infty$ for almost all $x$.
> 7. If $\int f=0$, then $f(x)=0$ for a.e. $x$.
> $\quad$ ^dd51c1

Note that $f_{n}(x)\geq 0$ and $f_{n}(x)\to f(x)$ for a.e. $x$ not necessarily imply $\int f_n \to \int f$. For example, consider $$f_{n}(x)=\begin{cases}n \quad \text{if } 0<x<1/n, \\ 0 \quad \text{otherwise.}\end{cases}$$Then $f_{n}(x)\to 0$ as $n\to\infty$ for every $x$, but $\int f_{n}=1$ for all $n$. Indeed, the limit of the integrals is greater than the integral of the limit function in general:

> [!lemma] Fatou's Lemma
> Suppose $\{f_n\}$ is a sequence of measurable functions with $f_n \geq 0$. If $\lim\limits_{n \to \infty} f_n(x) = f(x)$ for a.e. $x$, then  
> $$\int f \leq \liminf_{n \to \infty} \int f_{n}.$$

*Proof*  Suppose $0\leq g\leq f$, where $g$ is bounded and supported on a set $E$ of finite measure. And we let $g_{n}(x):=\min(g(x),f_{n}(x))$, then $g_{n}$ is measurable, supported on $E$, and $g_{n}\to g$ for a.e. $x$. By the [[Lebesgue Integration#^098e7e|bounded convergence theorem]], we have $$\int g_{n}\to \int g.$$ By construction, $g_{n}\leq f_{n}$, so that $\int g_{n}\leq\int f_{n}$ for all $n$, and therefore$$\int g= \liminf_{n\to \infty}\int g_{n}\leq \liminf_{n\to \infty}\int f_{n}$$by the definition of the limit inferior. Since $g$ is arbitrary, taking the supremum over all $g$ yields $\int f\leq \liminf_{n\to \infty}\int f_{n}$. $\square$

> [!theorem] Monotone Convergence Theorem
> Suppose $f$ is a non-negative measurable function, and $f_0\leq f_{1}\leq f_{2}\leq\cdots$ is a sequence of non-negative measurable functions, and $f_n(x) \to f(x)$ for almost every $x$. Then  
> $$\lim\limits_{n \to \infty} \int f_n = \int f.$$ ^230784

*Proof*  Since $f_{n}(x)\leq f(x)$ for a.e. $x$, by monotonicity, we have $\int f_{n} \leq \int f$, so $\limsup_{n\to \infty}\int f_{n} \leq \int f$. Hence, $$\int f \leq \liminf_{n \to \infty} \int f_{n}\leq\limsup_{n\to \infty}\int f_{n} \leq \int f,$$it follows that $\lim\limits_{n \to \infty} \int f_n = \int f$. $\square$

> [!comment]
> To simplify our notation, we shall write $f_{n}\nearrow f$ to mean that $f_{n}$ converges to $f$ in a nondecreasing sense, and $f_{n}\searrow f$ to mean that $f_{n}$ converges to $f$ in a nonincreasing sense.

> [!corollary] 
> Consider a series $\sum_{k=1}^{\infty} a_k(x)$, where $a_k(x) \geq 0$ is a measurable function for every $k \geq 1$. Then  
> $$\int \sum_{k=1}^{\infty} a_{k}(x) \dd x = \sum_{k=1}^{\infty} \int a_{k}(x) \dd x.$$  
> If $\sum_{k=1}^{\infty} \int a_{k}(x) \dd x$ is finite, then the series $\sum_{k=1}^{\infty} a_k(x)$ converges for a.e. $x$.

*Proof*  Let $f_{n}(x):=\sum_{k=1}^{n} a_{k}(x)$ and $f(x):=\sum_{k=1}^{\infty} a_{k}(x)$. Then $f_{n}$ and $f$ are measurable, and $f_{n}\nearrow f$, by the [[Lebesgue Integration#^230784|monotone convergence theorem]], we have $$\int \sum_{k=1}^{\infty}a_{k}=\int f=\int \lim_{n\to \infty} f_{n}=\lim_{n\to \infty}\int f_{n}=\sum_{k=1}^{\infty}\int a_{k}.$$If $\sum_{k=1}^{\infty}\int a_{k}$ is finite, then $\sum_{k=1}^{\infty} a_{k}$ is integrable, so $\sum_{k=1}^{\infty} a_{k}(x)$ is finite for a.e. $x$ by [[Lebesgue Integration#^dd51c1|the property 5]]. $\square$

## General Case

> [!definition] Lebesgue Integral of a Real-Valued Measurable Function  
> A real-valued measurable function $f$ on $\R^d$ is said to be Lebesgue integrable if the non-negative measurable function $|f|$ is integrable, i.e. $\int |f| < \infty$.
> If $f$ is Lebesgue integrable, its integral is defined as follows. We first define the positive and negative parts of $f$ by  
> $$f^+(x) := \max(f(x), 0), \quad f^-(x) := \max(-f(x), 0),$$  
> so that both $f^+$ and $f^-$ are non-negative and satisfy  
> $$f^+ - f^- = f.$$  
> Both functions $f^+$ and $f^-$ are integrable whenever $f$ is. We then define the Lebesgue integral of $f$ by  
> $$\int f = \int f^+ - \int f^-.$$ ^f4d3e6

> [!proposition]
> The integral of Lebesgue integrable functions is independent of the decomposition.

> [!proposition]
> The integral of Lebesgue integrable functions is linear, additive, monotonic, and satisfies the triangle inequality.
> 

> [!lemma] 
> Suppose $f$ is integrable on $\R^d$. Then for every $\epsilon > 0$:  
>  
> 1. **Existence of a finite measure set**: There exists a set of finite measure $B$ (a ball, for example) such that  
>    $$\int_{B^c} |f| < \epsilon.$$  
>  
> 2. **Absolute continuity of the integral**: There exists a $\delta > 0$ such that  
>    $$\int_E |f| < \epsilon \quad \text{whenever } m(E) < \delta.$$
> $\quad$

> [!theorem] Dominated Convergence Theorem
> Suppose $\{f_n\}$ is a sequence of measurable functions such that $f_n(x) \to f(x)$ a.e. as $n \to \infty$. If $|f_n(x)| \leq g(x)$, where $g$ is integrable, then  
> $$\int |f_n - f| \to 0 \quad \text{as } n \to \infty,$$  
> and consequently,  
> $$\int f_n \to \int f \quad \text{as } n \to \infty.$$

*Proof*  For each $N\geq 0$, let $E_{N}:=\{x\in\R^{d}\mid |x|\leq N, g(x)\leq N\}$. Fix $\epsilon>0$, by the previous lemma, 



<u><b>e.g.</b></u>  Consider functions $f_{n}(x)=\frac{x^n}{1+x^{n}}$. Clearly $\{f_{n}\}$ [[Convergence of Functions#^6eed8e|converges pointwise]]. However, it does not converge uniformly. But we can still say that $\lim_{n\to \infty}\int^{0}_{1} \lim_{n\to \infty}f_{n}(x)\dd x = \int^{0}_{1} f_{n}(x)\dd x$ by the dominated convergence theorem since $|f_{n}(x)|\leq 1$ and the constant function is integrable on $[0,1]$.
