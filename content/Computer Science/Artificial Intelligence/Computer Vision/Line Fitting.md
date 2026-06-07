## Random Sample Consensus

> [!algorithm]
**Algorithm**  <i><u>Random Sample Consensus (RANSAC)</u></i>
> 1. Sample (randomly) the minimum number of points required to fit the model ($n=2$ in case of line fitting).
> 2. Solve for model parameters.
> 3. Score by the fraction of inliers within a preset threshold.
> 4. Repeat until the best model is found.
> 
> The number of repetition $N$ is determined by equation of probability: $$1-\left(1-(1-\mathrm{e})^S\right)^N=p$$where $e$ is the probability that a point is an outlier, $s$ is the number of points in a sample and $p$ is the desired probability that we get a good sample.

>[!remark] 
>**Pros**:
>- Robust to outliers.
>- Applicable for large number of parameters.
>
>**Cons**:
> - Computational time grows quickly with the fraction of outliers and the number of parameters.
> - Not good for getting multiple line fits.
> - Can rapidly find a good model, not necessarily a great model.
> 
> **Common Applications**: Computing a rotation and translation between two images (will be used later for fundamental matrix in 2-view geometry).

## Hough Transform

>[!definition]
**Def**  <i><u>Hough Transform</u></i>
Let $D$ be the image space, $P$ be the parameter space of the shapes we're looking for. Let $H$ be the accumulator space, where each element represents a cell in the parameter space. Suppose $X = \{x_{i}\} \subset D$. Define a voting function $V(x, p)$ that takes a data point $x$ and a parameter vector $p$ in $P$. The Hough Transform for a set of data points $X$ is defined as the following integral over the parameter space $P$: $$H(p) = \int_{D} V(x, p) \dd x$$

>[!remark]
>The voting function typically outputs $1$ if $x$ is consistent with the shape defined by $p$, and $0$ otherwise. The integral essentially sums the votes for each cell (parameter vector) $p$ in the accumulator space $H$. Cells with high values in $H$ correspond to parameters that likely describe shapes present in the data points $X$.

>[!algorithm]
>**Algorithm**  <i><u>Hough Transform: Accumulator</u></i>


>[!algorithm]
>**Algorithm**  <i><u>Hough Transform: Polar Form</u></i>
>Use a polar representation for the parameter space: $$x\cos \theta + y\sin \theta = \rho$$Then A point $(x_{1}, y_{1})$ is mapped to a sinusoid in the polar parameter space $\theta-\rho$

>[!remark]
>Hough Transform: Pros and Cons
**Pros**:
> - All points processed independently, so can cope with occlusion
> - Some robustness to noise: noisy points are unlikely to contribute consistently to any single bin
> - Can detect multiple instances of line/circle/ellipse in a single pass
>
>**Cons**:
> - Complexity of search time increases exponentially with the number of model parameters.
> - Non-target shapes can produce spurious peaks in parameter space.
> - Quantization: hard to pick a grid size
> $\quad$



