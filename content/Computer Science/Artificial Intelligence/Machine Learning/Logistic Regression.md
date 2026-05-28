---
created: 2023-11-02
updated: 2024-10-23
---

## Hypothesis

$z = w \cdot x + b \\ \ \\ sigmoid(z)=\frac{1}{1+e^{-z}} \\ \ \\ f_{w,b}(x)=sigmoid(z)$

## Cost Function

$$L(w,b)=-y^{(i)}lnx^{(i)}+(y^{(i)}-1)ln(1-x^{(i)})\\ \ \\ J(w,b)=\frac {1} {m} \sum_{i=1}^mL(w,b)+\frac{\lambda}{2m}\sum_{j=1}^n w_j^2 $$