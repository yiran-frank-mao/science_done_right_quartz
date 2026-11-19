## Introduction
A Deep Declarative Network (DDN) is a type of deep learning model that allows for optimization problems to be embedded within an end-to-end learnable network. Instead of defining the forward function of each layer explicitly, a DDN defines the desired behavior of each layer implicitly by specifying an objective and constraints in a mathematical optimization problem. The output of each layer is then the solution of the optimization problem conditioned on the input and parameters. This approach enables the incorporation of complex data processing operations that are not easily expressed as explicit functions, such as projection, alignment, clustering, and matching. Moreover, DDNs can leverage the implicit function theorem to compute gradients through the implicit layers, enabling end-to-end learning with standard back-propagation algorithms.
![|350](https://i.imgur.com/jsoieVf.png)
## Contents
[[Declarative Node]]

## Acknowledgement
This part is mainly based on the ANU course [COMP4680](https://programsandcourses.anu.edu.au/2023/course/COMP4680) in 2023, convened by Prof. Stephen Gould, as well as his [notes](https://users.cecs.anu.edu.au/~sgould/papers/isaac22-lecture-notes.pdf) and [paper](https://arxiv.org/abs/1909.04866).