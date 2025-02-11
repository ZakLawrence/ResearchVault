---
tags:
  - Stats
---

# Basics of Probability 

Their are two main types of uncertainty, [[Types of Uncertainty]]

Probability represents a degree of beliefe in how likely a given phenomena is to be observed. Probabilities are described mathmatically, [[Definition of Probability]].  

With this mathmatical definition probabilities of a given event can be assigned 
1. Setup the sample space $\Omega$
2. For each element, $\omega$ in the set $\omega \in \Omega$ assign a probability to the element so $P(\omega)$ exists 
3. To find the probability of an event $A \in \Omega$ add all the elements in the event together so  $$P(A) = \sum\limits_{\omega \in A} P(\omega)$$

Any probability assigned must obey a set of [[Probability Axioms]]
For a set of events then oerations can be described as decribed bellow 

![[set-operations-venn-diagrams.png]]

The **Union** of two sets is denoted $A \cup B$, this is the space in either $A$ or $B$.

The **Intersection** of two sets is denoted $A \cap B$, this is the set of events in $A$ and $B$.

Two events are **mutually exclusive** if $A \cap B = \emptyset$, where $\emptyset$ is the **null set**

The probability for an event to be in the sets $A$ or $B$ can be expressed as $$ P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

