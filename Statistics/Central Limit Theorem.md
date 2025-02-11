---
tags:
  - Stats
---
## Central Limit Theorem
The **central limit theorem** states that the limit of a large number of measurements of a random variable $x_i$ the **sum of the random variables** will have a [[Gaussian distribution]] for its [[Probability density function]]

The random variable $x_i$ can have different means, $\mu_i$ and variances $\sigma_i$. The sum $z=\sum\limits_i x_i$ will be Gaussian distributed with a [[Mean]] $\mu = \sum\limits_i \mu_i$ and [[Standard deviation]] $\sigma = \sum\limits_i \sigma_i$

**The central limit theorem does not depend on how the underlying random variable is distributed**

## Proof 
First define 

$$y_i = \frac{x_i-\mu_i}{\sqrt{n}}$$

The [[Standard deviation]] of the variable $y_i$ is given by 
$$\sigma_{y_i}^2 = <y_i^2>-<y_i>^2 $$
$$= \frac{1}{n}<x_i^2 - 2x_i\mu_i+\mu_i> - \frac{1}{n}<x_i-\mu_i>^2$$
$$=\frac{1}{n}(<x_i^2>-\mu_j^2-<x_i>^2+\mu_i^2)$$ 
$$= \frac{1}{n}(<x_i^2>)-<x_i>^2) $$
$$= \frac{\sigma_i}{n}$$

The [[Expectation Value]] is given by 
$$<y_i> = \frac{1}{\sqrt{n}}<x_i-\mu_i> = \frac{1}{\sqrt{n}}(<x_i>-\mu_i) = 0$$

The [[Characteristic functions]] of $y_i$ is given by 
$$\phi_{y_j}(k) = \int f(y_j)e^{iky_j} = 1 + ik<y_j> + \frac{(ik)^2}{2}<y_j^2> + \cdots $$
$$\phi_{y_j}(k) = 1-\frac{k^2}{2}\frac{\sigma^2}{n}$$
Higher order terms are neglected.

The characteristic function for the sum $z$ is then given by 
$$\phi_{z}(k) = [1-\frac{k^2}{2}\frac{\sigma^2}{n}]^n \rightarrow e^{\frac{-k^2\sigma_j^2}{2}}$$
The p.d.f is then found by performing a [[Fourier transformation]]
$$f(z) = \frac{1}{2\pi} \int\limits_{-\infty}^{\infty}e^{-ikz}e^{\frac{-k^2\sigma^2}{2}}dk = \int\limits_{-\infty}^{\infty} e^{-(\frac{k\sigma}{\sqrt{2}}+\frac{iz\sqrt{2}}{\sigma})^2 - \frac{2z^2}{\sigma^2}} dk$$

$$u = \frac{k\sigma}{\sqrt{2}} + \frac{iz\sqrt{2}}{\sigma}$$                                                                
$$du = \frac{\sigma}{\sqrt{2}}dk$$

$$= \frac{1}{2\pi}e^{-2z^2/\sigma^2} \int\limits_{-\infty}^{\infty} e^{-u^2}dk = \frac{\sqrt2}{2\pi \sigma}e^{-2z^2/\sigma^2} \int\limits_{-\infty}^{\infty} e^{-u^2}du$$

The integral can be evaluated by converting to [[Polar coordinates]]
$$I = \int\limits_{-\infty}^{\infty} e^{-u^2}du \Rightarrow I^2 = \int\limits_{-\infty}^{\infty} e^{-(x^2+y^2)}dxdy$$
$$I^2 = \int\limits_{0}^{\infty} \int\limits_{0}^{2\pi}re^{-r^2}drd\theta = 2\pi \int\limits_{0}^{\infty}re^{-r^2}dr = \pi \int\limits_0^{\infty} e^vdv = \pi$$

Therefore $I = \sqrt\pi$. As such the p.d.f for $z$ becomes 

$$f(z) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{\frac{-z^2}{2\sigma^2}}$$

Which is a [[Gaussian distribution]] 

