The **Gaussian distribution** of a [[Continuous random variables]] is 
$$f(x;\mu,\sigma) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\bigg(\frac{-(x-\mu)^2}{2\sigma^2}\bigg)$$

where $\mu$ is the [[Mean]] and $\sigma$ is the [[Standard deviation]], these are so called due to the relations to the [[Expectation Value]] and [[Variance]].  These are given by  
$$<x> = \int\limits_{-\infty}^{\infty} x\frac{1}{\sqrt{2\pi\sigma^2}} \exp\bigg(\frac{-(x-\mu)^2}{2\sigma^2}\bigg)dx  = \mu$$
$$<(x-\mu)^2> =\int\limits_{-\infty}^{\infty} (x-\mu)^2\frac{1}{\sqrt{2\pi\sigma^2}} \exp\bigg(\frac{-(x-\mu)^2}{2\sigma^2}\bigg)dx = \sigma^2$$

A special case of the Gaussian distribution is when $\mu=0$ and $\sigma =1$, this defines the [[standard Gaussian]]. In the case that $y$ is a Gaussian distributed random variable with mean $\mu$ and standard deviation $\sigma$ then $x = \frac{y-\mu}{\sigma}$ is distributed according to a [[standard Gaussian]].  

The Gaussian distribution is important due the [[Central Limit Theorem]] that states that the sum of n independent [[Continuous random variables]] $x_i$ with means $\mu_i$ and variances $\sigma_i$ will be Gaussian distributed with a mean $\mu = \sum_i\mu_i$ and variance $\sigma^2 = \sum_i\sigma_i$

The $N$-Dimensional generalisation of the Gaussian distribution is 
$$f(\vec{x};\vec{\mu},V) = \frac{1}{(2\pi)^{N/2} |V|^{1/2}} \exp \bigg[ -\frac{1}{2} (\vec{x}-\vec{\mu})^{T} V^{-1}(\vec{x}-\vec{\mu})\bigg] $$

#Stats 



