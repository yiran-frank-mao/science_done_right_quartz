> [!definition] Directed Graph
> A *directed graph*, also called a *digraph*, is a graph in which the edges have a direction. A directed graph is an ordered pair $G = (V, E)$ where $V$ is a set whose elements are called *vertices* or *nodes*. $E$ is a set of ordered pairs of vertices, called *arcs* or *directed edges*. A digraph thus consists of two functions, source $s \colon E \to V$ and target $t \colon E \to V$. ^4d934f


**Def**  <i><u>Path</u></i>
A path is a finite sequence of edges $e_{1}, \dots , e_{n}$ in a graph such that $t(e_{i}) = s(e_{i+1})$ for all $i=1,2,\dots,n-1$. ^b6d4f2

**Def**  <i><u>Directed Graph Homomorphism</u></i>
Directed graph homomorphism is a mapping of edges to edges and vertices to vertices that preserves sources and targets.