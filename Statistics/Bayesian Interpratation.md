---
tags:
  - Stats
---
In this case elements of the sample space are interpreted as a hypotheses. The probabilities are then interpreted as a degree of belief in the hypothesis.

$$P(A) = \text{degree of belief that A is true}$$

The sample space must be constructed such that the elementary hypotheses are mutually exclusive so that only one is true. A subset that contains multiple hypotheses is said to be true if any of the hypotheses in the subset are true.

Hypotheses can be statements such that a measurement will give an outcome a certain fraction of the time, In so this interpretation contains the frequentest interpretation.

An advantage of the Bayesian approach is that probabilities can be assigned to unknown parameters to fall withing a given range, this would not make sense in the frequentest approach as the measurements would either either be in the range or not giving either a 1 or a 0. With this approach we can assign a probability to measure the parameter in a given range.

In this approach we can also consider the question of what is the probability that a theory is true given some data, this means that
$$P(\text{theory|data}) \propto P(\text{data|theory})\cdot P(\text{theory})$$
where $P(\text{theory})$ is the prior probability that the theory is true, $P(\text{data|theory})$ is the likelihood which is the probability to observe the data under a given hypothesis. The method for assigning the prior probability assigned to the theory is not predefined so a suitable prior must be chosen to represent the initial degree of belief in the hypothesis. This is one of the reasons that the Bayesian approach is more subjective than the frequentest.

