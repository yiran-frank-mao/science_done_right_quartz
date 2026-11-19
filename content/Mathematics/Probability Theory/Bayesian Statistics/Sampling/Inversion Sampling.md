**Prop**  If $X\sim F(x)$, then $F(x)\sim \mathcal{U}(0,1)$.
**Proof**  $$\pr( F(X)\leq x)=\pr(X\leq F^{-1}(x))=F(F^{-1}(x))=x$$Thus $F(x)\sim \mathcal{U}(0,1)$.

**Algorithm**  <i><u>Inversion Sampling</u></i>
To draw $n$ samples from CDF $F(x)$, we can
1. Draw $u_{1},\dots,u_{n} \sim \mathcal{U}(0,1)$
2. Set $x_{i}=F^{-1}(u_{i})$
3. Return $x_{1},\dots,x_{n}$ as iid samples from $F(x)$.
<u><b>e.g.</b></u> Assume $Y$ is an exponential random variable with rate parameter $λ=2$. Recall that the probability density function is $p(y)=2\exp(-2y)$ for $y>0$. First, we compute the CDF:$$F_Y(x)=P(Y\leq x)=\int_0^x2e^{-2y}dy=1-e^{-2x}$$Solving for the inverse CDF, we get that $$F_Y^{-1}(y)=-\frac{\ln(1-y)}2$$Using our algorithm above, we first generate $u_{i}\sim\mathcal{U}(0,1)$, then set $x_{i}=F_{Y}^{-1}(u_{i})=-\frac{\ln(1-u_{i})}2$. We do this in the R code below and compare the histogram of our samples with the true density of $Y$:
```R
# inverse transform sampling
num.samples <-  1000
U           <-  runif(num.samples)
X           <- -log(1-U)/2

# plot
hist(X, freq=F, xlab='X', main='Generating Exponential R.V.')
curve(dexp(x, rate=2) , 0, 3, lwd=2, xlab = "", ylab = "", add = T)
```
![invsamp|600](https://i.imgur.com/3gsL0Ci.png)