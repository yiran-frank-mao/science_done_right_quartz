---
created: 2024-01-22
updated: 2024-09-24
---
## Sample Space and Probability Space

> [!definition] Sample Space
> The sample space $\Omega$ of an experiment is the set of all possible outcomes of the experiment. An event $A$ is a subset of the sample space $\Omega$, and we say that $A$ occurred if the actual outcome is in $A$. ^9cf9be

> [!definition] Probability Measure
> A probability measure $P$ on a [[Measurable Spaces and Functions#^0bddf6|measurable space]] $(X,\mathcal{S})$ is a [[Measurable Spaces and Functions#^c2e020|measure]] that $P(X)=1$.

> [!definition] Probability Space
> A probability space $(\Omega, \mathcal{F}, P)$ is a a mathematical construct that provides a formal model of a random process, where
> - $\Omega$ is a sample space, which is the set of all possible outcomes.
> - $\mathcal{F}$ is an event space, which is a [$\sigma$-algebra](Measurable%20Spaces%20and%20Functions#^60a516) over $\Omega$.
> - $P\colon \mathcal{F}\to[0,1]$ is a a probability measure, which assigns, to each event a probability.
> $\quad$ ^c9205a

## Random Variable

> [!definition] Random Variable and Probability
> Let $(\Omega, \mathcal{F}, P)$ be a probability space, and $(E,\mathcal{E})$ a measurable space. Then an $(E,{\mathcal {E}})$-valued random variable is a [[Measurable Spaces and Functions#^11c83a|measurable function]] $X\colon \Omega \to E$. Then the *probability* that $X$ takes on a value in a measurable set $S\subseteq E$ is written as$$\pr(X\in S)=P\left(\left\{\omega\in\Omega\mid X(\omega)\in S\right\}\right).$$ ^a0b9ff
