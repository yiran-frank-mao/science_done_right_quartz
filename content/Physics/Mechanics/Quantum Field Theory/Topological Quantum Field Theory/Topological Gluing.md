> [!theorem] Regular Interval Theorem
> Let $M\colon\Sigma_{0} \to \Sigma_{1}$ be a [[Cobordisms#^4998ff|cobordism]], and let $f\colon M\to [0,1]$ be a [[Morse Functions and Critical Points#^c50e9c|Morse function]] without any critical points, then there is a diffeomorphism from the cylinder $\Sigma_{0}\times [0,1]$ to $M$ that is compatible with the projection to $[0,1]$:
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/regular_interval_theorem.svg" alt="regular_interval_theorem" style="width:25%;"/>
> And similarly there is another diffeomorphism $\Sigma_{1}\times[0,1] \to M$ compatible with the projection.

> [!corollary]
> Let $M\colon \Sigma_{0}\to \Sigma_{1}$ be a [[Cobordisms#^4998ff|cobordism]]. Then there is a decomposition $M=M_{[0,\varepsilon]}M_{[\varepsilon, 1]}$ such that $M_{[0,\varepsilon]}$ is diffeomorphic to the cylinder $\Sigma_{0}\times [0,\varepsilon]$. 
> 

*Proof*  Take a Morse function $f\colon M\to [0,1]$, then there is some  $\varepsilon>0$ such that $f$ has no critical points in $M_{[0,\varepsilon]}:=f^{-1}([0,\varepsilon])$. By the regular interval theorem, there is a diffeomorphism $\Sigma_{0}\times [0,\varepsilon]\to M_{[0,\varepsilon]}$. $\square$

## Gluing of General Cobordisms

> [!theorem]
> Suppose $M\colon \Sigma_{0}\to \Sigma_{1}$ and $N\colon \Sigma_{1}\to \Sigma_{2}$ are [[Cobordisms#^4998ff|cobordisms]], then there always exists a [[Manifolds and Atlases#^6ef2ef|smooth manifold]] $NM$ which is [[Isometries and Homeomorphisms#^85034b|homeomorphic]] to $M\sqcup_{\Sigma_{1}}N$ and whose smooth structure agrees with both $M$ and $N$. ^a3afdb

