---
tags:
  - Stats
---
The **$\chi^2$ test** evaluates the agreement of data with a distribution. 

When dealing with a distribution of data it is best to consider the level of agreement of a [[Hypothesis]] across all the bins. 

The **observed** number of events in a given bin is $n_i$.
The **Expected** number of events in a given bin is $\nu_i$

If the distribution of events in each bin follows a [[Poisson distribution]] then the **$\chi^2$ test** provides a measure of agreement between the data to the predictions. 

$$\chi^2 = \sum\limits_i \frac{(n_i - \nu_i)^2}{\nu_i}$$
The value of this follows a [[Chi2 distribution]]. 

