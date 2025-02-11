**Multivariate functions** of [[Random Variables]]  are [[Functions of Random Variables]] that take multiple random variables as inputs. for these the joint [[Probability density function]] is given by 
$$g(a')da' = \int \cdots \int_{dS}f(x_1,\cdots , x_n ) dx_1 \cdots dx_n$$

In the case that there are $n$ random variables $\vec{x} = (x_1,\cdots,x_n)$ and a set of $n$ linearly independent functions $a_i(\vec{x})$ that can be inverted to give $x_i(a_1,\cdots,a_n)$ the joint p.d.f is given  by 
$$g(a_1,\cdots,a_n) = f(x_1,\cdots,x_n)|J|$$
$$J = \begin{pmatrix} \frac{\partial x_1}{\partial a_1} &\frac{\partial x_1}{\partial a_2} & \cdots & \frac{\partial x_1}{\partial a_n} \\ \frac{\partial x_2}{\partial a_1} &\frac{\partial x_2}{\partial a_2} & \cdots & \frac{\partial x_2}{\partial a_n} \\ \vdots &\vdots&\ddots & \vdots\\ \frac{\partial x_n}{\partial a_1} &\frac{\partial x_n}{\partial a_2} & \cdots & \frac{\partial x_n}{\partial a_n} \end{pmatrix}$$
where $J$ is the [[Jacobian]]


[[Multivariate Functions Example]]
Tags: #Stats 