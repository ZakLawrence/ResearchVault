The **conditional probability** of two events $A$ & $B$ is the probability for the event $A$ to occur **given $B$ has occurred** this is written as $P(A|B)$. 

$$P(A|B) = \frac{P(A\cap B)}{P(B)}$$

The expression can also be used for $P(B|A)$

$$P(B|A) = \frac{P(A\cap B)}{P(A)}$$

As such they can be related by the relation 

$$P(A|B) = \frac{P(B|A)P(A)}{P(B)}$$

In some cases it can be more practical to divide the sample into subsets so $\Omega = \bigcup_{i}A_{i}$  where the sets are disjoint, $A_i \cap A_j = \emptyset$,$\forall i\neq j$. The event $B$ can be expressed in terms of this 
$$B = B\cap \Omega = B\cap(\bigcup_{i}A_{i}) = \bigcup_{i}(B\cap A_{i})$$
$$P(B) = P(\bigcup_{i}(B\cap A_{i})) = \sum\limits_i P(B\cap A_i)$$

Substituting into the above equation gives **Bayes Theorem**
$$P(A|B) = \frac{P(B|A)P(A)}{\sum\limits_i P(B\cap A_i)}$$

Tags: #Stats 