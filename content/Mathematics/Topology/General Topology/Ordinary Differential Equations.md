>[!definition] Ordinary Differential Equation
>An ordinary differential equation (ODE) is an equation that relates a function $x(t)$ of single variable $t ∈ I$ with its derivatives, where $I$ denotes an interval. If the highest derivative appeared in the equation is the $n$-th derivative $x^{(n)}(t)$, it is called an $n$-th ODE. The general form of n-th order ODE takes the form $$F(t,x(t),x^{\prime}(t),\cdots,x^{(n)}(t))=0,\quad t\in I$$A function $x \colon I →\R$ is called a solution of an $n$-th order ODE if $x$ has continuous derivatives up to order $n$ such that plugging $x(t),x^{\prime}(t),\cdots,x^{(n)}(t)$(t) into the equation gives an identity for each $t ∈ I$.

<u><b>e.g.</b></u>  Consider the motion of a spring with one endpoint fixed. let $x(t)$ denote its displacement. According to [[Newtonian Mechanics#^957b58|Newton’s second law]], $$F=mx^{\prime\prime}(t)$$where m denotes the mass of the spring. According to [[Newtonian Mechanics#^f63b06|Hooke’s law]], we have $F = −kx(t)$, where $k > 0$ is a constant. Then we obtain $$mx^{\prime\prime}(t)+kx(t)=0$$which is a 2nd order ODE.

>[!definition] Initial Value Problem
>An initial value problem for an $n$-th order ODE takes the form$$\begin{aligned}x^{(n)}(t)=G(t,x(t),x^{\prime}(t),\cdots,x^{(n-1)}(t)),\quad t\in I\\x(t_0)=u_0,x^{\prime}(t_0)=u_1,\cdots,x^{(n-1)}(t_0)=u_{n-1}\end{aligned}$$

>[!proposition] 
>Any initial value problem of an $n$-th order ODE can be transformed into an equivalent first order system of ODEs.

*Proof*  Set $x_{i}(t)=x^{(i-1)}(t)$ for all $i\leq n$. Then let $$x=\begin{pmatrix}x_1\\\vdots\\x_{n-1}\\x_n\end{pmatrix},\quad f(t,x)=\begin{pmatrix}x_2\\\vdots\\x_n\\G(t,x_1,\cdots,x_n)\end{pmatrix},\quad x_0=\begin{pmatrix}u_0\\\vdots\\u_{n-2}\\u_{n-1}\end{pmatrix},$$then we have $$\left\{\begin{array}{l}x^{\prime}(t)=f(t,x(t)),\quad t\in I\\x(t_0)=x_0\end{array}\right.$$which is an initial value problem of a first order system of ODEs.

>[!theorem] Peano’s Existence Theorem
>Let $U ⊂\R×\R^{n}$ be an open set, let $f \colon U →\R^{n}$ be a continuous function on $U$, and let $(t_{0},x_{0}) ∈ U$. Then the initial value problem $$x(t)=f(t,x(t)),\quad x(t_0)=x_{0}$$has a solution defined on $[t_{0},t_{0} +h]$ for some $h > 0$.

