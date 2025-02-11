[[Multivariate Functions]]

Considering the example of the random variables $x$ and $y$ which are distributed according to the [[Probability density function]] $g(x)$ and $h(y)$. The product of the random variables $z = xy$. If we assume that $x$ and $y$ are [[Independent]] then the joint p.d.f is given by $g(x)h(y)$

$$f(z)dz = \int\int_{dS} g(x)h( y) dxdy = \int_{dS} g(x)dx \int_{dS}h(y)dy$$
$$=\int\limits_{-\infty}^{\infty} g(x)dx \int\limits_{\frac{z}{|x|}}^{\frac{z+dz}{|x|}}h(y)dy = \int\limits_{-\infty}^{\infty} g(x)h(z/x) \frac{dz}{x}dx$$
$$f(z) = \int\limits_{-\infty}^{\infty} g(x) h(z/x)\frac{dx}{x}$$

This is an example of a [[Mellin Convolution]] of the functions $g(x)$ and $h(y)$. If we instead consider $z = x+y$ then the p.d.f will be given by the [[Fourier Convolution]] of the function

Tags: #Stats 