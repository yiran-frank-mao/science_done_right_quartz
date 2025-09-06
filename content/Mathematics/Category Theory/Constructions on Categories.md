>[!definition] Product Category
>The product of two categories $\mathbf{C}$ and $\mathbf{D}$, written $\mathbf{C}\times \mathbf{D}$, has objects of the form $(C,D)$ for $C\in\obj \mathbf{C}$ and $D\in\obj\mathbf{D}$, and morphisms of the form $(f,g)\colon(C,D)\to(C^{\prime}, D^{\prime})$ for $f\colon C\to C^{\prime}$ and $g\colon D\to D^{\prime}$. Composition and units are defined componentwise. That is$$(f^{\prime},g^{\prime})\circ(f,g)=(f^\prime\circ f,g^\prime\circ g),\quad1_{(C,D)}=(1_C,1_D)$$There are two obvious projection functors:$$\mathbf{C}\xleftarrow{\pi_1}\mathbf{C}\times\mathbf{D}\xrightarrow{\pi_2}\mathbf{D}$$defined by $π_1(C,D) = C$ and $π_1(f,g) = f$, and similarly for $π_2$.

>[!definition] Diagonal Functor
>Define the diagonal functor $\Delta\colon \mathbf{C} \to\mathbf{C}\times\mathbf{C}$ such that $$\Delta(X)=( X,X ),\quad \Delta(f\colon X\to Y)=f\times f \colon X\times X \to Y\times Y$$

**Prop**  For any $A\times B$ and $C \times D$ in $\mathbf{C}$, 

>[!definition] Opposite Category
>The *opposite* or *dual category* $\mathbf{C}^\text{op}$ of a category $\mathbf{C}$ has the same objects as $\mathbf{C}$, and an arrow $f \colon A \to B$ in $\mathbf{C}^\text{op}$ is an arrow $f \colon B \to A$ in $\mathbf{C}$. That is $\mathbf{C}^\text{op}$ is just $\mathbf{C}$ with all of the arrows formally turned around. 
>It is convenient to have a notation to distinguish an object in $\mathbf{C}$ from the same one in $\mathbf{C}^\text{op}$. Thus we may write$\bar{f}\colon\bar{B}\to\bar{A}$ in $\mathbf{C}^\text{op}$ for $f \colon A\to B$ in $\mathbf{C}$. With this notation we can define composition and units in $\mathbf{C}^\text{op}$ in terms of the corresponding operations in $\mathbf{C}$, namely$$1_{\bar{C}}=\bar{1_C},\quad\bar{f}\circ{\bar{g}}=\bar{g\circ f}.$$

<u><b>e.g.</b></u>  Consider a simple $\mathbf{Cat3}$: ![dualcat|450](https://i.imgur.com/NoPVoa8.png)

>[!definition] Arrow Category
>The *arrow category* $\mathbf{C}^{\rightarrow}$ of a category $\mathbf{C}$ has the arrows of $\mathbf{C}$ as objects, and an arrow $g$ from $f\colon A\to B$ to $f^{\prime}\colon A^{\prime} \to B^{\prime}$ in $\mathbf{C}^{\rightarrow}$ is a commutative square:
>![|250](https://i.imgur.com/mu8bpHL.png)
>where $g_{1}$ and $g_{2}$ are arrows in $\mathbf{C}$. That is, such an arrow is a pair of arrows $g = (g_{1}, g_{2})$ in $\mathbf{C}$ such that $g_2\circ f=f^{\prime}\circ g_1$. The identity arrow $1_{f}$ on an object $f :\colon A \to B$ is the pair $(1_{A},1_{B})$. Composition of arrows is done componentwise:$$(h_1,h_2)\circ(g_1,g_2)=(h_1\circ g_1,h_2\circ g_2)$$

**Prop**  Observe that there is a functor $\dom\colon \mathbf{C}^{\rightarrow}\to\mathbf{C}$.

>[!definition] Slice Category
>The *slice category* $\mathbf{C}/C$ of a category $\mathbf{C}$ over an object $C\in\obj \mathbf{C}$ has all arrows $f \in\mor\mathbf{C}$ such that $\cod(f) = C$ as objects and $g$ from $f \colon X \to C$ to $f^{\prime} \colon X^{\prime} \to C$ is an arrow $g \colon X \to X^{\prime}$ in $\mathbf{C}$ such that $f^{\prime} \circ g = f$, as indicated in:
><img src="https://i.imgur.com/muDP5Da.png" alt="" style="width:25%;"/>
>with identity arrow $1_{f}=1_{X}$ and composition law inherits from $\mathbf{C}$. ^8b8420

>[!definition] 
>**Def**  <i><u>Coslice Category</u></i>
>The coslice category $C/\mathbf{C}$ of a category $\mathbf{C}$ under an object $C\in\obj \mathbf{C}$ has as objects all arrows $f$ of $\mathbf{C}$ such that $\dom (f) =C$, and an arrow from $f \colon C \to X$ to $f^{\prime} \colon C \to X^{\prime}$ is an arrow $h \colon X \to X^{\prime}$ such that $h\circ f = f^{\prime}$: 
>![|250](https://i.imgur.com/6MQcyjP.png)
>We have identity arrow $1_{f}=1_{X}$ and composition law inherits from $\mathbf{C}$.
><u><b>e.g.</b></u>  Consider the category $\mathbf{Sets_*}$ of pointed sets consists of sets $A$ with a distinguished element $a ∈ A$, and arrows $f \colon (A,a) \to (B,b)$ are functions $f \colon A \to B$ that preserves the points, $f(a) = b$. This is isomorphic to the coslice category:$$\mathbf{Sets}_{*}\cong\{*\}/\mathbf{Sets}$$where $\{*\}$ is the singleton. Indeed the functor $$F\colon \{*\}\to A, \quad (f\colon\{*\}\to X)\mapsto(X,f(*))$$is an isomorphism.

**Prop**  For any category $\mathbf{C}$ and its object $C$, we have $C/\mathbf{C}\cong\mathbf{C}^\text{op}/C$.
**Proof**  