Functions of [[Random Variables]] are functions that take a random variabel as an input. **They are themselves random variables**.

## Definitions
> If $a(x)$ is a **Continuous Function** of the  [[Continuous random variables]] $x$, that is distributed according to the p.d.f $f(x)$ then $a(x)$ will be distributed by the p.d.f $g(a)$

The two distributions are related by requiring that the probability to find the variable $x$ in the interval $[x,x+dx]$ is equal to the probability to find $a(x)$ in the interval $[a,a+da]$

$$P(x\leq X \leq x+dx) = P(a \leq A \leq a+da)$$

Or equivalently 
$$g(a')da' = \int\limits_{dS}f(x)dx$$

The integral is performed over the region $dS$ which is the region in $x$ in which the function is between $a(x) = a'$ and $a(x) = a'+da'$. In some cases this can be disjoint as shown bellow. 

![[Functions of random variables.png]]

In the case that the function can be uniquely inverted to obtain $x(a)$ then 
$$g(a)da = \int\limits_{x(a)}^{x(a + da)}f(x)dx =\int\limits_{x(a)}^{x(a)+\bigg| \frac{dx}{da}\bigg|da}f(x)dx$$
Evaluating the integral with use of the [[Taylor expansion]] 
$$= F(x(a)+\bigg| \frac{dx}{da}\bigg|da) - F(x(a)) $$
$$= F(x(a)) + f(x(a))\bigg| \frac{dx}{da}\bigg|da - F(x(a))$$
Therefore 
$$g(a) = f(x(a)) \bigg| \frac{dx}{da}\bigg|$$

## Properties
### Expectation Value
The [[Expectation Value]] of a function of a random variable is given by 
$$<a(\vec{x})> = \int\limits_{-\infty}^{\infty}a(\vec{x})f(\vec{x})dx_1\cdots dx_n = \int\limits_{-\infty}^{\infty} a(\vec{x})g(a(\vec{x}))da $$
Integrating over the full space of the function $a(\vec{x})$

### Covariance
For two functions of random variables the [[Covariance]] is given by 
$$\text{cov}(a(\vec{x}),b(\vec{y})) = V_{ab} = \int a(\vec{x})b(\vec{y})g(a(\vec{x}),b(\vec{y})) da db - <a(\vec{x})><b(\vec{y})> $$

the terms $V_{ab}$,$V_{ba}$,$V_{aa}$ and $V_{bb}$ for element of a matrix where $V_{aa} = \sigma_a^2$ and $V_{bb} = \sigma_b^2$. The terms $V_{ab} = V_{ba}$ meaning the matrix is symmetric

This [[Correlation]] can be obtained from this. 

If two random variables are [[Independent]] then the covariance is 
$$<(x-\mu_x)(y-\mu_y)> = \int\limits_{-\infty}^{\infty}xyf(x,y)dxdy - \mu_x \mu_y = \int\limits_{-\infty}^{\infty}xf(x)dx \int\limits_{-\infty}^{\infty}yf(y)dy - \mu_x \mu_y $$
$$=  \mu_x \mu_y -  \mu_x \mu_y = 0$$
As such the covariance of independent random variables will be zero 

Tags: #Stats 