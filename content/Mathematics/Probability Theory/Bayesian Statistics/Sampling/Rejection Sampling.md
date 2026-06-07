**Algorithm** <i><u>Rejection Sampling</u></i>
We want to sample from PDF $f(x)$, but this is difficult to do. Suppose we have proposed PDF $g(x)$, then we can:
1. Generate $x^{\star}$ from $g(x)$
2. Accept $x^\star$ with probability $\frac{f(x^\star)}{Kg(x^\star)}$
Or equivalently,
1. Generate $x^{\star}$ from $g(x)$
2. Generate $y^\star$ from $\mathcal{U}(0,Kg(x^\star))$
3. Accept $x^\star$ if $y^{\star}\leq f(x^{\star})$
where we require $f (x) \leq Kg(x)$ for all $x$. For efficiency, we can let $K=\max_{x}\frac{f(x)}{g(x)}$.
![rejSamp|500](https://i.imgur.com/8FNA2j8.png)