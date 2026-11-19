---
cssclasses:
  - img-grid
---
**Thrm**  Any waveform in time or space can be uniquely expressed as a sum over different frequencies of the correct phase and amplitude.

**Thrm** Suppose we have a function $f(x)$ that specifies over a domain $0$ to $\lambda$ and has period $\lambda$. And it satisfies the Dirichlet's conditions:
- It has a finite integral over the domain.
- It has a finite number of extrema over the domain.
- It has a finite number of non-infinite discontinuities over the domain.
Then it is possible to express this function as an infinite sum of harmonic functions:$$ f(x)=\frac{a_0}{2}+\sum_{n=1}^{\infty} \left( a_n \cos \left(2 \pi n v_0 x\right)+b_n \sin \left(2 \pi n v_0 x\right) \right)
$$where $v_0=\frac{1}{\lambda}$ is the lowest frequency term in the series.

**Prop**  The above parameters are given by:
$$
\begin{aligned}& a_0=2 v_0 \int_0^\lambda f(x) d x \\& a_n=2 v_0 \int_0^\lambda f(x) \cos \left(2 \pi n v_0 x\right) d x \\& b_n=2 v_0 \int_0^\lambda f(x) \sin \left(2 \pi n v_0 x\right) d x\end{aligned}
$$
- The constant $\frac{a_0}{2}$ is the average of $f(x)$
- If $f(x)-\frac{a_0}{2}$ is even, it will be built out of only cosine functions
- If $f(x)-\frac{a_0}{2}$ is odd, it will be built out of only sine functions.

**Prop**  <i><u>Alternative form of Fourier Series</u></i>
Let $k_0$ be the angular frequency, and $k_n=nk_0$ we will have:
$$f(x)=\frac{1}{2 \pi} \sum_{n=-\infty}^{\infty} C_n e^{i k_n x} \\ \text { where } C_n=A_n-i B_n=k_0 \int_{-\pi / k_0}^{\pi / k_0} f(x) e^{-i k_n x} d x$$

**Def**  <i><u>The Gibbs Phenomenon</u></i>
For a step discontinuity, the overshoot is 9% on each side of the step. As you increase the number of terms the width of the overshoot tends to zero but the amplitude is constant.

![gibbs_phenomenon.svg](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/gibbs_phenomenon.svg)
![gibbs_phenomenon_2.svg|65%](https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/gibbs_phenomenon_2.svg)
