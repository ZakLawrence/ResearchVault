$n$ measurements of the a [[Random Variables]] $x$ which is described by a [[Probability density function]] $f(x)$ are made, if they are [[Independent]] then the resulting p.d.f if 
$$f(x_1,\cdots,x_n) = f(x_1)\cdots f(x_n)$$
Often the form of $f(x)$ is not known so a hypothesised function us used.
This function has the form $f(x;\vec{\theta})$ where $\vec{\theta}$ are a set of parameters used to get the form of the p.d.f 

A [[Statistic]] can be built from the observed data $\vec{x}$ to estimate the parametrs $\theta$. This is an [[Estimator]]. If it [[Converges]] the the true value of the parameter then it is said to be **Consistent**

Since an [[Estimator]] is a function of the [[Random Variables]] $\vec{x}$ the they themselves are [[Random Variables]] and will be described by a [[Probability density function]] $g(\hat{\theta};\theta)$, this is often reffered to as the [[Sampling Distribution]].  

Estimators can have a [[Bias]], in the case that the bias goes to zero as $n\rightarrow\infty$ then the estimator is **asymptotically unbiased** 

The **Mean Square Error** is given by 
$$\text{MSE} = <(\hat{\theta}-\theta)^2> = $$


Tags: #Stats 