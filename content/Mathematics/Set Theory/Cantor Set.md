> [!definition] Cantor Set
> The (“middle third”) Cantor set is constructed as follows:
> 0. Set $C_{0} = [0, 1]$.
> 1. Remove the middle third (as an open interval) of this set, leaving $C_1=[0,\frac{1}{3}]\cup[\frac{2}{3},1]$.
> 2. From each of $2^{N−1}$ closed intervals from $C_{N−1}$ remove the open middle third to give a new set that consists of $2^{N}$ closed intervals.
> Note that $C_N$ consists of $2^N$ closed intervals, each of length $3^{−N}$ (so their total length is $(2/3)^N \to0$, as $N\to\infty$). Now the set $C=\bigcap_{n=0}^\infty C_n$ is the (middle third) Cantor set. ^d4ff78

**Prop**  Since each $C_n$ is closed, $C$ is closed (as it is the intersection of closed sets). 
**Prop**  C is non-empty: it contains the endpoints of every interval that we remove (in fact it contains uncountably many points, which we will prove later).