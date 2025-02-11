---
tags:
  - Stats
---
## Limiting case of probability distribution 
The characteristic function can be used to get the behaviour of the probability distribution in the limiting case, for example the [[binomial distribution]] has the characteristic function 
$$\phi(k) = [p(e^{ik}-1)+1]^N$$
If we take the large sample limit with $p\rightarrow 0$, $N\rightarrow 0$ and $\nu \rightarrow pN$ then 
$$\phi(k) = [\frac{\nu}{N}(e^{ik}-1)+1]^N \rightarrow exp[\nu(e^{ik}-1))]$$
which is the characteristic function of the [[Poisson distribution]]

## p.d.f for a function of a random variable
The p.d.f for a function of random variable can be obtained if the p.d.f for the random variable is known. 
For example $X_i$ have the p.d.f $f_i(x)$, and the function $Z = \sum\limits_i X_i$. The p.d.f for $Z$ can be obtained from the characteristic function 
$$\phi_{Z}(k) = \prod\limits_{i=1}^{n}\int e^{ik\sum_i x_i}f_i(x)dx_i = \prod_{i=1}^{n}\phi_i(k)$$
Which can be inverted to give the p.d.f


