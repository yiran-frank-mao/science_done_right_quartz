---
updated: 2025-05-03
completed: true
---
## Variations

The calculus of variations is concerned with the extremals of functions whose domain is an infinite-dimensional space: the space of curves. Such functions are called functionals.

> [!definition] Differentiable Functional
> A functional $\newcommand{\dd}{\:\mathrm{d}}\newcommand{\ddf}[2]{\frac{\mathrm{d}#1}{\mathrm{d}#2}}\Phi$ on the space of $C^{\infty}$ functions is called differentiable if $\Phi(\gamma+h)-\Phi(\gamma)=F(h)+R(h,\gamma)$, such that $F$ depends linearly on $h$ and $R(h,\gamma)$ is a remainder term that $R(h,\gamma)=O(h^{2})$ in the sense that for $|h|<\varepsilon$ and $|\ddf{h}{t}|<\varepsilon$, we have $|R(h,\gamma)|<c\varepsilon^{2}$ for some positive constant $c$.
> $F$ is called the differential or variation of $\Phi$ at $\gamma$, denoted as $\delta_{\gamma} \Phi$.

> [!proposition]
> Suppose $\Phi\colon C^{\infty}(\R, \R^{n})\to\R$ is a differentiable functional of curves, and $\varphi\colon \R^{n}\to \R^{n}$ is a $C^{2}$ (not necessarily linear) map of coordinate change. If we identify $\varphi$ as a transformation that change the coordinate of every point on a curve, then the functional after changing the coordinate, $\Phi\circ \varphi$, is also a differentiable functional on $C^{\infty}(\R, \R^{n})$.
> 

*Proof*  Fix some arbitrary curve $\gamma\in C^\infty(\R,\R^{n})$, for any $h\in C^\infty(\R,\R^{n})$ and any $t\in\R$, since $\varphi$ is differentiable, we can write $$\newcommand{\D}{\mathrm{D}}\varphi(\gamma(t)+h(t))=\varphi(\gamma(t))+\D_{\gamma(t)}\varphi(h(t)) + Q(h(t),\gamma(t)),$$where $\D_{\gamma(t)}\varphi$ is the differential of $\varphi$ at $\gamma(t)$, and $Q(h(t),\gamma(t))$ is a remainder term that satisfies $\|h(t)\|<\varepsilon$ will imply $\|Q(h(t),\gamma(t))\|<c\varepsilon^{2}$ for some constant $c$. As the above holds for all $t$, we shall abuse our notation and identify $\varphi(\gamma)$, $\D_{\gamma}\varphi (h)$ and $Q(h,\gamma)$ to be the curve in $C^\infty(\R,\R^{n})$ such that $$\varphi(\gamma)(t):=\varphi(\gamma(t)),\quad\D_{\gamma}\varphi (h) (t):=\D_{\gamma(t)}\varphi (h(t)),\quad Q(h,\gamma)(t):=Q(h(t),\gamma(t)).$$Hence the above equation can be rewritten without $t$:$$\varphi(\gamma+h)=\varphi(\gamma)+\D_{\gamma}\varphi(h)+Q(h,\gamma).$$Now we consider the differentiable functional $\Phi$ at $\varphi(\gamma)$, for which we denote $F:=\delta_{\varphi(\gamma)}\Phi$ be the variation of $\Phi$ at $\varphi(\gamma)$. Then we have the following equation hold: $$\begin{aligned}\Phi(\varphi(\gamma+h)) - \Phi(\varphi(\gamma)) - F(\D_{\gamma}\varphi(h)) = \Phi(\varphi(\gamma)+\D_{\gamma}\varphi(h)+Q(h,\gamma)) - \Phi(\varphi(\gamma)) - F(\D_{\gamma}\varphi(h)). \end{aligned}$$To simplify our notation, let $A:=\D_{\gamma}\varphi(h)+Q(h,\gamma)$, then we have $$\begin{aligned}&\,\Phi(\varphi(\gamma+h)) - \Phi(\varphi(\gamma)) - F(\D_{\gamma}\varphi(h)) \\
=&\, \Phi(\varphi(\gamma)) + F(A) + R(A,\varphi(\gamma)) - \Phi(\varphi(\gamma)) - F(\D_{\gamma}\varphi(h)) \\
=&\, F(\D_{\gamma}\varphi(h)) +F(Q(h,\gamma)) + R(A,\varphi(\gamma))- F(\D_{\gamma}\varphi(h))\\
=&\, F(Q(h,\gamma)) + R(A,\varphi(\gamma)),
\end{aligned}$$where the first equation is by differentiability of $\Phi$, the second equation is by the linearity of $F$.
Without loss of generality, pick some small $1>\varepsilon>0$, suppose $\|h\|<\varepsilon$ and $\left\|\ddf{h}{t}\right\|<\varepsilon$, we have $\|Q(h,\gamma)\|<c_{1}\varepsilon^{2}$ for some constant $c_{1}>0$. Since $F$ is linear, we have $F(Q(h,\gamma))<c_{2}\|Q(h,\gamma)\| <c_{2}c_{1}\varepsilon^{2}$ for some positive constant $c_{2}$. Moreover, $\D_{\gamma}\varphi$ is also linear, so $$\|A\|=\|\D_{\gamma}(h)+Q(h,\gamma)\|\leq \|\D_{\gamma}(h)\| + \|Q(h,\gamma)\|<c_{3}\varepsilon + c_{1}\varepsilon^{2}<(c_{3}+c_{1})\varepsilon,$$for some positive constant $c_{3}$. Similarly, $\left\|\ddf{A}{t}\right\|$ satisfies: $$\left\|\ddf{A}{t}\right\|\leq \left\| \ddf{D_{\gamma}(\varphi)(h)}{h}\cdot \ddf{h}{t}\right\| + \left\| \ddf{Q(h,\gamma)}{h}\cdot \ddf{h}{t}\right\|<c_{3}\varepsilon+c_{4}\varepsilon,$$because $\left\|\ddf{D_{\gamma}(\varphi)(h)}{h}\right\|$ is bounded by $c_{3}$, $\left\|\ddf{Q(h,\gamma)}{h}\right\|$ is bounded by some $c_{4}$, and $\left\|\ddf{h}{t}\right\|$ is bounded by $\varepsilon$. Set $c:=\max\{c_{3}+c_{1},c_{3}+c_{4}\}$, then both $\|A\|$ and $\left\|\ddf{A}{t}\right\|$ are bounded by $c\varepsilon$. Therefore, there holds $$R(A,\varphi(\gamma))<c' (c\varepsilon)^{2} = c'c^{2} \varepsilon^{2},\quad \text{for some constant } c'>0.$$Thus, $$F(Q(h,\gamma)) + R(A,\varphi(\gamma))<c_{2}c_{1}\varepsilon^{2} +c'c^{2} \varepsilon^{2}=(c_{2}c_{1}+c'c^{2}) \varepsilon^{2},$$which means $\Phi(\varphi(\gamma+h)) - \Phi(\varphi(\gamma)) - F(\D_{\gamma}\varphi(h))=O(h^{2})$, so $\Phi\circ \varphi$ is differentiable, and $\delta_{\varphi(\gamma)}(\Phi\circ \varphi )= \delta_{\gamma}\Phi \circ \D_{\gamma}\varphi$. $\square$


> [!proposition]
> Suppose $\newcommand{\R}{\mathbb{R}}L\colon \R^{n}\times \R^{n}\times \R \to \R$. The functional $\newcommand{\dd}{\:\mathrm{d}} \Phi(x):=\int_{t_{0}}^{t_{1}} L(x(t),\dot{x}(t),t)\dd t$ is differentiable, and its derivative is given by $$\newcommand{\ddf}[2]{\frac{\dd #1}{\dd #2}}\newcommand{\pddf}[2]{\frac{\partial#1}{\partial#2}} \delta_{x}\Phi(h)=\int_{t_{0}}^{t_{1}}\left( \pddf{L}{x} - \frac{\dd}{\dd t} \frac{\partial L}{\partial \dot{x}}\right)h \dd t + \left.\left( \frac{\partial L}{\partial \dot{x}} h\right)\right|_{t_{0}}^{t_{1}}$$
> ^2ed65d

*Proof*  This is achieved by taking Taylor expansion, and then integral by parts. $\square$

## Euler-Lagrange Equation

> [!definition] Extremal
> An extremal of a differentiable functional $\Phi$ is a curve $\gamma$ such that $\delta_{\gamma}\Phi=0$. ^aa327b

> [!lemma]
> If a [[Continuity of Functions#^f56121|continuous]] real function $f$ defined on $[t_{0},t_{1}]$ satisfies $\int_{t_{0}}^{t_{1}} f(t)h(t)\dd t=0$ for all $h\in C^{\infty}_{0}(t_{0},t_{1})$ with $h(t_{0})=h(t_{1})=0$, then $f=0$. ^3f133e

*Proof*  We prove by contradiction. Suppose $f(t^{*})>0$ for some for some $t^{*}$. Since $f$ is continuous, $f(t)>c$ in some open ball $B_{\varepsilon}(t^*)$ of the point $t^{*}$. Let $h$ be a smooth function such that $h(t)>0$ in $U$, $h(t)=0$ outside of $U$, and $h(t)=1$ in $B_{\varepsilon/2}(t^*)$. Then, clearly, $\int_{t_{0}}^{t_{1}} f(t)h(t)\dd t \geq c\varepsilon>0$. This yields a contradiction, so $f(t)=0$ for all $t$. $\square$

> [!theorem] Euler-Lagrange Equation
> Suppose $L\colon \R^{n}\times \R^{n}\times \R \to \R$. The curve $\gamma$ is an extremal of the functional $\Phi(x):=\int_{t_{0}}^{t_{1}} L(x(t),\dot{x}(t),t)\dd t$ on the space of smooth curves passing through the points $x_{0}$ and $x_{1}$ if and only if it satisfies
> $$ \frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{\gamma}(t)} \right) - \frac{\partial L}{\partial \gamma(t)}=0,\quad \text{for all } \gamma(t).$$
> This is called the Euler-Lagrange equation for the functional.

*Proof*  By the preceding [[Variational Calculus#^2ed65d|proposition]], we know $$\delta_{x}\Phi(h)=\int_{t_{0}}^{t_{1}}\left( \pddf{L}{x} - \frac{\dd}{\dd t} \frac{\partial L}{\partial \dot{x}}\right)h \dd t + \left.\left( \frac{\partial L}{\partial \dot{x}} h\right)\right|_{t_{0}}^{t_{1}}.$$Since $\Phi$ is defined on the space of smooth curves passing through points $x_{0}$ and $x_{1}$, we require $h(t_{0})=h(t_{1})=0$, thus the second term vanishes. Therefore, by definition, the extremal is achieved when $$\delta_{x}\Phi(h)=\int_{t_{0}}^{t_{1}}\left( \pddf{L}{x} - \ddf{}{t}\pddf{L}{\dot{x}}\right)h \dd t=0.$$By the above [[Variational Calculus#^3f133e|lemma]], it follows that $\pddf{L}{x} - \ddf{}{t}\pddf{L}{\dot{x}}=0$ at all time. The converse is true trivially. $\square$

> [!theorem]
> The condition for a curve $\gamma$ to be an extremal of a functional does not depend on the coordinate system.

*Proof*  Suppose we have two coordinate systems $x$ and $y$ to describe same curve $\gamma$. Then, the Euler-Lagrange equation in $x$ coordinates is $$\begin{aligned}
0&=\frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{x}} \right) - \frac{\partial L}{\partial x} \\
&= \frac{\dd }{\dd t} \left( \frac{\partial L}{\partial y}\frac{\partial y}{\partial \dot{x}} + \frac{\partial L}{\partial \dot{y}} \frac{\partial \dot{y}}{\partial\dot{x}} + \frac{\partial L}{\partial t}\frac{\partial t}{\partial\dot{x}} \right) -\frac{\partial L}{\partial y} \frac{\partial y}{\partial x} - \frac{\partial L}{\partial\dot{y}}\frac{\partial \dot{y}}{\partial x} - \frac{\partial L}{\partial t}\frac{\partial t}{\partial x} \\
&= \frac{\dd }{\dd t} \left( \frac{\partial L}{\partial y}\frac{\partial y}{\partial \dot{x}} + \frac{\partial L}{\partial \dot{y}} \frac{\partial \dot{y}}{\partial\dot{x}} \right) -\frac{\partial L}{\partial y} \frac{\partial y}{\partial x} - \frac{\partial L}{\partial\dot{y}}\frac{\partial \dot{y}}{\partial x}.
\end{aligned}$$Note that $y$ is a coordinate transformed from $x$, so $y=y(x)$. Thus $\dot{y}=\frac{\partial y}{\partial x} \dot{x}$, so $\frac{\partial \dot{y}}{\partial \dot{x}}=\frac{\partial y}{\partial x}$. Therefore the above equation can be written as $$\begin{aligned}
0 &= \frac{\dd }{\dd t} \left( \frac{\partial L}{\partial y}\frac{\partial y}{\partial \dot{x}} + \frac{\partial L}{\partial \dot{y}} \frac{\partial \dot{y}}{\partial\dot{x}} \right) -\frac{\partial L}{\partial y} \frac{\partial y}{\partial x} - \frac{\partial L}{\partial\dot{y}}\frac{\partial \dot{y}}{\partial x}\\
&= \frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{y}} \frac{\partial y}{\partial x} \right) -\frac{\partial L}{\partial y} \frac{\partial y}{\partial x} - \frac{\partial L}{\partial\dot{y}}\frac{\partial \dot{y}}{\partial x}\\
&= \frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{y}}  \right) \frac{\partial y}{\partial x} + \frac{\partial L}{\partial \dot{y}}\frac{\dd}{\dd t}\left(\frac{\partial y}{\partial x} \right) -\frac{\partial L}{\partial y} \frac{\partial y}{\partial x} - \frac{\partial L}{\partial\dot{y}}\frac{\partial \dot{y}}{\partial x}\\
&= \left(\frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{y}}  \right) -\frac{\partial L}{\partial y}\right) \frac{\partial y}{\partial x} + \frac{\partial L}{\partial \dot{y}} \left( \frac{\dd}{\dd t}\left(\frac{\partial y}{\partial x} \right)  -\frac{\partial \dot{y}}{\partial x} \right)\\
&= \left(\frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{y}}  \right) -\frac{\partial L}{\partial y}\right) \frac{\partial y}{\partial x} + \frac{\partial L}{\partial \dot{y}} \left( \frac{\partial^{2}y}{\partial x^{2}}\dot{x} -\frac{\partial }{\partial x} \left( \frac{\partial y}{\partial x} \dot{x}\right)\right)\\
&= \left(\frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{y}}  \right) -\frac{\partial L}{\partial y}\right) \frac{\partial y}{\partial x} + \frac{\partial L}{\partial \dot{y}} \left( \frac{\partial^{2}y}{\partial x^{2}}\dot{x} -\frac{\partial^{2}y}{\partial x^{2}}\dot{x}\right)\\
&= \left(\frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{y}}  \right) -\frac{\partial L}{\partial y}\right) \frac{\partial y}{\partial x}.
\end{aligned}$$Clearly $\frac{\partial y}{\partial x}$ is non-zero, so $\frac{\dd }{\dd t} \left( \frac{\partial L}{\partial \dot{y}}  \right) -\frac{\partial L}{\partial y}=0$, which is the Euler-Lagrange equation in $y$ coordinates. $\square$

> [!remark]
> This is an important point, because it helps us get coordinate independent descriptions of mechanical systems.

> [!definition] Beltrami Identity
> The Beltrami identity for some function $f(y_1,y_2,\dots,y_n,\dot{y_1},\dot{y_2},\dots,\dot{y_n},x)$ is defined as $$ \text{Id}_{\text{Beltrami}}=\sum^{n}_{i=1}\dot y_{i}\frac{\partial f}{\partial \dot y_i} - f $$

> [!proposition]
> For any $f(y_1,y_2,\dots,y_n,\dot{y_1},\dot{y_2},\dots,\dot{y_n},x) = f(y_1,y_2,\dots,y_n,\dot{y_1},\dot{y_2},\dots,\dot{y_n})$, we have the Euler-Lagrange Equation is equivalent to $\text{Id}_{\text{Beltrami}}=\text{constant}$.

Here is one example of variational calculus in optics:

> [!principle] Fermat’s Principle
> Fermat's Principle states that the path taken by a light ray between two points is the one that requires the least time. Mathematically, this principle can be expressed as $\delta \int n ds = 0$, where $n$ is the index of refraction and $s$ is the distance traveled by the light ray.
