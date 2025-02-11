The **Uniform distribution** for a [[Continuous random variables]] is defined as 
$$f(x;\alpha,\beta) = \bigg\{ \begin{array}{c 1} \frac{1}{\beta - \alpha} & \quad \alpha \leq x \leq \beta \\ 0 & \quad \text{otherwise}\end{array}$$
The uniform distribution gives a probability to observe a value within a given range as being equal to the size of that range.  
The [[Expectation Value]] for the uniform distribution is
$$<x> = \int\limits_{\alpha}^{\beta}\frac{x}{\beta-\alpha}dx = \frac{1}{2}(\alpha+\beta)$$
The [[Variance]] is 
$$<(x-<x>)^2> = \int\limits_{\alpha}^{\beta} (x-\frac{1}{2}(\alpha+\beta))^2\frac{1}{\beta-\alpha} = \frac{1}{12} (\beta -\alpha)^2$$

For any randomly distributed variable it can be transformed into one that is uniformly distributed. Taking the random variable $x$ with p.d.f $f(x)$ and [[Cumulative distribution]] $F(x)$, then the random variable $y=F(x)$ will be uniformly distributed. 

This can be shown by getting the expression for $g(y)$. 
$$\frac{dy}{dx} = \frac{d}{dx} \int\limits_{-\infty}^{x}f(x')dx' = f(x)$$

As such 
$$g(y) = f(x)\bigg|\frac{dx}{dy}\bigg| = 1$$

#Stats 


