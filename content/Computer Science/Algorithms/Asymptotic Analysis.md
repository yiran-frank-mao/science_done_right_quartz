---
updated: 2025-02-12
completed:
---
## Asymptotic Notations Table

| Notation                          | Approx.   | Growth                        | Test                                                            |
| --------------------------------- | --------- | ----------------------------- | --------------------------------------------------------------- |
| $f(n)=o{\bigl(}g(n){\bigr)}$      | $<$       | Strictly smaller than $g(n)$  | $\lim_{n\to\infty}{\frac{f(n)}{g(n)}}=0$                        |
| $f(n)=O{\bigl(}g(n){\bigr)}$      | $\leq$    | At most as large as $𝑔(𝑛)$  | $\lim_{n\to\infty}{\frac{f(n)}{g(n)}}=0 \text{\ or \ } c$       |
| $f(n)=\Omega{\bigl(}g(n){\bigr)}$ | $\geq$    | At least as large as $𝑔(𝑛)$ | $\lim_{n\to\infty}{\frac{f(n)}{g(n)}}=\infty \text{ \ or \ } c$ |
| $f(n)=\omega{\bigl(}g(n){\bigr)}$ | $>$$\>$   | Strictly larger than $g(n)$   | $\lim_{n\to\infty}{\frac{f(n)}{g(n)}}=\infty$                   |
| $f(n)=\Theta{\bigl(}g(n){\bigr)}$ | $\approx$ | The same growth as $g(n)$     | $\lim_{n\to\infty}{\frac{f(n)}{g(n)}}=c$                        |
##  Properties of Asymptotic Notations

> [!proposition] Transitivity
> The following properties hold:
> - $f(n)=\Theta\bigl((g(n)\bigr) \text{ and } g(n)=\Theta\bigl(h(n)\bigr) \implies f(n) = \Theta\bigl(h(n)\bigr)$
> - $f(n)=O\bigl((g(n)\bigr) \text{ and } g(n)=O\bigl(h(n)\bigr) \implies f(n) = O\bigl(h(n)\bigr)$
> - $f(n)=\Omega\bigl((g(n)\bigr) \text{ and } g(n)=\Omega\bigl(h(n)\bigr) \implies f(n) = \Omega\bigl(h(n)\bigr)$
> - $f(n)=o\bigl((g(n)\bigr) \text{ and } g(n)=o\bigl(h(n)\bigr) \implies f(n) = o\bigl(h(n)\bigr)$
> - $f(n)=\omega\bigl((g(n)\bigr) \text{ and } g(n)=\omega\bigl(h(n)\bigr) \implies f(n) = \omega\bigl(h(n)\bigr)$
> $\quad$

> [!proposition] Reflexivity
> The following properties hold:
> - $f(n)=\Theta(f(n))$
> - $f(n) = O(f(n))$
> - $f(n) = \Omega(f(n))$
> $\quad$

>[!proposition] Symmetry & Transpose Symmetry
>The following properties hold:
>- $f(n)=\Theta\bigl((g(n)\bigr) \iff g(n)=\Theta\bigl((f(n)\bigr)$.
>- $f(n)=O\bigl((g(n)\bigr) \iff g(n)=\Omega\bigl((f(n)\bigr)$.
>- $f(n)=o\bigl((g(n)\bigr) \iff g(n)=\omega\bigl((f(n)\bigr)$.
>$\quad$

> [!proposition]
> Asymptotic notations are not [[Preorder, Partial Order and Posets#^a8688d|linear ordering]].

> [!proposition]
> $𝑎 (\log 𝑛)^k = 𝑜(𝑛)$ for any positive constants $𝑎 > 0$ and integer $𝑘 > 0$.

*Proof*  We can prove by repeatedly applying the L’Hopital’s rule: $$ \lim_{n \to \infty} \frac{a(\log n)^k}{n}=0 $$ $\square$