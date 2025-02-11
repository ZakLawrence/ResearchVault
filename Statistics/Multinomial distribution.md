The **Multinomial distribution** is the  generalisation of the [[binomial distribution]] to the case where there are more than two possible outcomes. 

In the case of $m$ possible outcomes and the probability for an outcome $i$ is $p_i$. The probabilities must be constrained so that $\sum\limits_{i=1}^{m}p_i =1$

In the case of $N$ measurements then the total number of possible sequences with $n_1$ measurements of type 1, $n_2$ measurements of type 2, ect is given as 
$$\frac{N!}{n_1!n_2!\cdots n_m!}$$
If the order of the outcomes is not important then the probability to observe this is given by 
$$f(n_1,n_2,\cdots,n_m) =\frac{N!}{n_1!n_2!\cdots n_m!} p_1^{n_1}p_2^{n_2}\cdots p_m^{n_m} $$

Since we can imagine the case we are interested in just the events $i$ then it stands to reason that we would have a [[binomial distribution]] for observing $i$, giving a [[Expectation Value]] $<n_i> = Np_i$ and [[Variance]] $V[n_i] = Np_i(1-p_i)$

If on the other hand we are interested in three possibilities of type $i$, $j$ and the rest then is given by 
$$f(n_i,n_j) =\frac{N!}{n_i!n_j!(N-n_i-n_j)!} p_i^{n_i}p_j^{n_j}(1-p_i-p_j)^{N-n_i-n_j}$$

The [[Covariance]] $V_{ij}$ is then $V_{ij} = -Np_ip_j$

An example of a multinational distribution is the is the probability to obtain a particular result of a histogram with N entries and m bins and where $n_i$ is the bin content of bin $i$. From the equation for the covariance we expect that the bin content of any two bins will be negatively correlated.

#Stats 

