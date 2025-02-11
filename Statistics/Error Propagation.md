Often for a set of random variables $\vec{x}$ we may not know the exact form of the [[Probability density function]] $f(\vec{x})$ but may have estimates of $\vec{\mu}$ and $V_{ij}$

For a function $y(\vec{x})$ the p.d.f is typically obtained by $g(y) = \int_{dS}f(\vec{x})d\vec{x}$ however, we don't know $f(\vec{x})$ so we need to estimate the [[Expectation Value]] and [[Variance]] 

Performing a [[Taylor expansion]] of $y(\vec{x})$ about $\vec{x} = \vec{\mu}$ 
$$y(\vec{x}) = y(\vec{\mu}) + \sum\limits_{i=1}^{n} \frac{\partial y}{\partial x_i} \bigg|_{\vec{x} = \vec{\mu}}(x_i-\mu_i) $$

Then the estimate for the expectation value is 
$$<y(\vec{x})> = \int\limits_{-\infty}^{\infty}y(\vec{x})g(y)dy = \int\limits_{-\infty}^{\infty} y(\vec{x}) f(\vec{x}) d\vec{x}$$
$$\approx \int\limits_{-\infty}^{\infty} ( y(\vec{\mu}) + \sum\limits_{i=1}^{n} \frac{\partial y}{\partial x_i} \bigg|_{\vec{x} = \vec{\mu}}(x_i-\mu_i)) f(\vec{x})d\vec{x} = y(\vec{\mu})$$

The estimate for $<y^2(\vec{x})>$ is given by 
$$<y^2(\vec{x})> = y^2(\vec{\mu}) + \sum\limits_{i,j}^{n}\bigg[ \frac{\partial y}{\partial x_i}\frac{\partial y}{\partial x_j}\bigg]_{\vec{x} = \vec{\mu}}V_{ij}$$

Then the estimate for the variance is given by 
$$\sigma_y^2 =\sum\limits_{i,j}^{n}\bigg[ \frac{\partial y}{\partial x_i}\frac{\partial y}{\partial x_j}\bigg]_{\vec{x} = \vec{\mu}}V_{ij}$$

If we are dealing with a set of functions $y_1(\vec{x}), \cdots , y_m(\vec{x})$ the [[Covariance]] matrix is given as 

$$U_{kl} = \sum\limits_{i,j}^{n}\bigg[ \frac{\partial y_k}{\partial x_i}\frac{\partial y_l}{\partial x_j}\bigg]_{\vec{x} = \vec{\mu}}V_{ij}$$

Which is a **Matrix Transformation** , $U = A V A^{T}$ where the transformation matrix is given by 
$$A_{ij} = \bigg[\frac{\partial y_i}{\partial x_j} \bigg]_{\vec{x} = \vec{\mu}}$$

Tags: #Stats 