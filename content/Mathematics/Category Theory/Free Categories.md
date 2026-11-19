>[!definition] Category on Graph
>Given a [[Basics of Graphs#^4d934f|directed graph]] $G=(V,E)$, we define the category $\mathsf{C}(G)$ generated from $G$ by taking the vertices of $G$ as objects, and the [[Basics of Graphs#^b6d4f2|paths]] in $G$ as arrows, we shall write the arrows of $\mathsf{C}(G)$ in the form $e_{n}e_{n−1}\dots e_{1}$ and define$$\dom(e_{n}e_{n−1}\dots e_{1})=s(e_{1}),\quad \cod(e_{n}e_{n−1}\dots e_{1})=t(e_{n})$$and define composition by concatenation:$$e_{n}\dots e_{1}\circ e^{\prime}_{m}\dots e^{\prime}_{1} = e_{n}\dots e_{1} e^{\prime}_{m}\dots e^{\prime}_{1}$$For each vertex $v$, we have an empty path denoted $1_{v}$, which is the identity arrow at $v$.

>[!proposition] 
> If $G$ has only one vertex, then $\mathsf{C}(G)$ is just the free monoid on the set of edges of $G$.

>[!proposition] 
> If $G$ has only vertices (no edges), then $\mathsf{C}(G)$ is the discrete category on the set of vertices of $G$.

**Def**  <i><u>Universal Mapping Property</u></i>
