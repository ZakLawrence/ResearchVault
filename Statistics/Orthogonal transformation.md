For a set of [[Random Variables]] $x_i$ it can sometimes be useful to transform to a new set $y_i$ such that the [[Covariance]] matrix is diagonal. 
To do so use a [[Linear transformation]] where 
$$y_i = \sum\limits_{j=1}^{n}A_{ij}x_j$$
The covariance matrix is then given by 
$$\text{COV}(y_i,y_j) = \sum\limits_{k,l}A_{ik}V_{kl}A^{T}_{lj}$$
Where the matrix $A$ must be determined so that the covariance matrix is diagonal. 
This is done by finding the [[Eigen Vectors]] of the covariance matrix $V$.
Given that the covariance matrix is symmetric the eigen vectors will be **Orthogonal**.
$$U_{ij} =\sum\limits_{k,l}A_{ik}V_{kl}A^{T}_{lj} =\sum\limits_{k,l} r^i_k V_{kl} r^j_l = \sum\limits_{k,l}r^i_k \lambda_j r^j_l $$
$$= \lambda_j \vec{r}^i\cdot\vec{r}^j = \lambda_j \delta_{ij}$$

Tags: #Stats 