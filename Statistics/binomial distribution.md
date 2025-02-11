---
tags:
  - Stats
---
$$ f(n;N,p) = \frac{N!}{n!(N-n)!}p^n(1-p)^{N-n}$$

The **binomial distribution** for [[Discrete random variables]] is encountered in case where there are a set of observations with two possible outcomes, either **success** or **failure** where the probability of success is $p$. 

The **total number of successes $n$** is a [[Discrete random variables]]
The **binomial distribution** describes how $n$ is distributed. 
The value of the function is the **Probability** to observe **$n$ successes** and **$N-n$ faliures**
The [[Expectation Value]] is given by 
$$<n> = \sum\limits_{n=1}^{\infty} n \frac{N!}{n!(N-n)!}p^n(1-p)^{N-n} = Np \sum\limits_{n=1}^{\infty}  \frac{(N-1)!}{(n-1)!(N-n)!}p^{n-1}(1-p)^{N-n}$$
$$= Np(p+(1-p))^{n-1} = Np$$
This uses the [[binomial Theorem]]

The [[Variance]] of the distribution 
$$<n^2> = <n(n-1) + n> = Np\sum\limits_{n=1}^{\infty}  (n-1)\frac{(N-1)!}{(n-1)!(N-n)!}p^{n-1}(1-p)^{N-n} +Np$$
$$= N(N-1)p^2 \sum\limits_{n=1}^{\infty} \frac{(N-2)!}{(n-2)!(N-n)!}p^{n-2}(1-p)^{N-n}  + Np$$

Therefore 
$$<n^2> - <n>^2 = N(N-1)p^2 + Np - (Np)^2 = Np(1-p)$$

