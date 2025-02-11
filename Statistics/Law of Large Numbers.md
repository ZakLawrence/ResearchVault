The **Law of Large Numbers** describes the behaviour of the result of performing the same experiment a large number of times. When a variable is being measured a large number of times the [[Mean]] of the measurements will converge to the [[Expectation Value]] of the variable being measured.

For a set of random variables ${x_i}$ where each has a [[Expectation Value]] $<x_i> = \mu$. The average of these variables will converge to $\mu$ as the number of random variables considered approaches infinity, $Z_N \rightarrow \mu$ as $N \rightarrow \infty$

$$Z_N = \sum\limits_{i=0}^{N}\frac{x_i}{N}$$
The [[Characteristic functions]] for the terms $\frac{x_i}{N}$ is given by 
$$\phi_{\frac{x_i}{N}}= \int f_i(x)e^{\frac{ikx_i}{N}}dx_i$$


Performing a [[Taylor expansion]] 
$$e^{\frac{ikx}{N}} = \sum \limits_{j=0}^{\infty}(\frac{ikx}{N})^j\frac{1}{j!}$$

Substituting into the characteristic function gives 
$$\phi_{\frac{x_i}{N}} = \int f_i(x)[1+\frac{ikx_i}{N} + \cdots]dx_i = 1 + \frac{ik<x_i>}{N}+\cdots$$

Letting $N \rightarrow \infty$ means that the higher order terms can be neglected. Therefore the characteristic function for the average $Z_N$ will tend to 
$$\phi_{Z_N} \simeq [1+\frac{ik\mu}{N}]^N \Rightarrow e^{ik\mu}$$

The p.d.f for the average is given by the [[Fourier transformation]] 
$$f_{Z_N}(z) = \frac{1}{2\pi}\int e^{-ik(z-\mu)}dk = \delta(z-\mu)$$
Therefore the p.d.f tends to a [[delta function]] centred on $\mu$

Tags: #Stats 