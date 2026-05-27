> [!definition] Frobenius Object
> A *Frobenius object* in a [[Monoidal Categories#^bc017c|monoidal category]] $\newcommand{\one}{\mathbb{1}}(\mathsf{C}, \otimes, \one)$ is an object $A$ equipped with four morphisms
> $$\eta\colon \one\to A,\quad \mu\colon A\otimes A\to A, \quad \delta\colon A \to A\otimes A, \quad \varepsilon\colon A\to \one, $$ 
> such that $(A,\mu, \eta)$ is a monoid object, $(A, \delta, \varepsilon)$ is a comonoid object, and the Frobenius relation holds:
> 
> <img src="https://raw.githubusercontent.com/yiran-frank-mao/image_repo/master/Obsidian/Frobenius_object_Frobenius_relation.svg" style="width:40%;"/>

<u><b>e.g.</b></u>  A Frobenius object in $(\mathsf{Vect}_{\mathbb{K}}, \otimes, \mathbb{K})$ is precisely a Frobenius algebra.

> [!definition] Frobenius Homomorphism
> A *Frobenius homomorphism* between two Frobenius objects $(A,\mu_{A},\eta_{A},\delta_{A},\varepsilon_{A})$ and $(B,\mu_{B},\eta_{B},\delta_{B},\varepsilon_{B})$ is a morphism $f\colon A \to B$ that is both a monoid homomorphism and a comonoid homomorphism. 
> Thus the Frobenius objects together with Frobenius homomorphisms form a category, denoted by $\mathsf{Frob}(\mathsf{C})$. 
> 

## The Universal Frobenius Structure

