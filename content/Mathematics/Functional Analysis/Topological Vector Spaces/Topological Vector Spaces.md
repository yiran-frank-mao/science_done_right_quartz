> [!definition] Topological Vector Space
> A *topological vector space* is a [[Vector Spaces#^f4b63e|vector space]] that is also a [[Topological Spaces#^concept-39ce12df888c|topological space]], where the vector space operations (addition and scalar multiplication) are [[Continuous Maps on Topological Spaces#^33ee5a|continuous]] with respect to the topology. ^dd5802

<u><b>e.g.</b></u>  Banach spaces, Hilbert spaces, and Sobolev spaces are all examples of topological vector spaces.

> [!proposition]
> Suppose $X$ is a topological vector space. Fix some $x_{0}\in X$, then the translation map $T_{x_{0}}\colon X\to X$, $x\mapsto x+x_{0}$ is a homeomorphism. Therefore, any topological vector space is topologically homogeneous.
> 

*Proof*  Suppose $\alpha\colon X\times X\to X$ is the addition. Then every translation map is a composition: $$ T_{x_{0}}\colon  X \xrightarrow{\cong} \{*\}\times X \xrightarrow{c_{x_{0}}\times\operatorname{id}} X \times X \xrightarrow{\alpha} X, $$where each map is continuous. So $T_{x_{0}}$ is continuous. Its inverse is $T_{-x_{0}}$, which is also continuous. $\square$




> [!definition] Complete Topological Space
> A *Cauchy net* in a topological vector space $X$ is a [[Countability Axioms and Nets#^ed5107|net]] $(x_{\alpha})_{\alpha\in A}$ such that for every [[Closure, Interior and Boundary#^eda962|open neighborhood]] $U$ of $0$, there exists $\alpha_{0}\in A$ such that for all $\alpha,\beta\gtrsim \alpha_{0}$, $x_{\alpha}-x_{\beta}\in U$.
> A topological vector space is *complete* if any Cauchy net converges to a point in the space.

Usually the completeness is defined with respect to a metric, 

> [!theorem]
> For a topological vector space $X$, $X$ is $T_{0}$ iff it is $T_{1}$ iff it is $T_{2}$ ([[Mathematics/Topology/General Topology/Separation and Hausdorff Spaces#^f7bcc8|Hausdorff]]).
> 





## References
- [Maria Infusino, Topological Vector Spaces (2017)](https://www.math.uni-konstanz.de/~infusino/TVS-SS17/teachingSS2017.html).
- [Dietmar Vogt, Lectures on Fréchet Spaces](http://www2.math.uni-wuppertal.de/~vogt/vorlesungen/fs.pdf).
- [Paul Garrett, Seminorms and locally convex spaces](https://www-users.cse.umn.edu/~garrett/m/fun/notes_2012-13/07b_seminorms.pdf).
