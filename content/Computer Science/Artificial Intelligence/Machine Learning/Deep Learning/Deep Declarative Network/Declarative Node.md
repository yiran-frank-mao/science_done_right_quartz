**Def**  <i><u>Declarative Node</u></i>
The declarative node is a node in a neural network such that the input-output relationship specified as solution to an optimization problem:
![decNode|400](https://i.imgur.com/hAlaZ5x.png)
<b><u>e.g.</u></b> Suppose we have an imperative specification that $y(x)=\frac{1}{n}\sum_{i=1}^nx_i$, then the corresponding declarative specification is $y=\operatorname{argmin}_{u\in \mathbb{R}^n} \sum_{i=1}^n \| u-x_i \|_2^2$.