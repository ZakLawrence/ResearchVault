The **Poisson distribution**  for [[Discrete random variables]] can be seen a limiting case of the [[binomial distribution]] where $N\rightarrow \infty$ and $p\rightarrow0$ but the [[Expectation Value]] $Np = \nu$ where $\nu$ is a **finite** value. 

To show that the [[binomial distribution]] gives the **Poisson distribution** in this limit we can make use of the [[Characteristic functions]]. See [[Applications of Characteristic functions]]. 

$$f(n;\nu) = \frac{\nu^n}{n!}e^{-\nu}$$

The [[Expectation Value]] is given by 
$$<n> = \sum\limits_{n=0}^{\infty}n\frac{\nu^n}{n!}e^{-\nu} = \nu$$

The [[Variance]] is given by 
$$V[n] = \sum\limits_{n=0}^{\infty}(n-\nu)^2\frac{\nu^n}{n!}e^{-\nu} = \nu$$

If we consider a Poisson distribution with a large mean then in this limit we can treat the variable as continuous and following a [[Gaussian distribution]].

An example of where the Poisson distribution may be encountered is in the expected number of events in a scattering experiment, where $L$ is the [[Luminosity]], $\sigma$ is the [[Cross section]]  and $\epsilon$ is the efficiency (the probability to observe in the detector). $\nu = L\sigma\epsilon$

#Stats 

