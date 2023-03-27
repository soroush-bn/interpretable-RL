
## Abstract

Although deep reinforcement learning has become a promising machine learning approach
for sequential decision-making problems, it is still not mature enough for high-stake do-
mains such as autonomous driving or medical applications. In such contexts, a learned
policy needs for instance to be interpretable, so that it can be inspected before any de-
ployment (e.g., for safety and veriability reasons). This survey provides an overview of
various approaches to achieve higher interpretability in reinforcement learning (RL). To
that aim, ==we distinguish interpretability (as a property of a model) and explainability (as
a post-hoc operation==, with the intervention of a proxy) and discuss them in the context
of RL with an emphasis on the former notion. In particular, we argue that interpretable
RL may embrace dierent facets: ==interpretable inputs, interpretable (transition/reward)
models, and interpretable decision-making==. Based on this scheme, we summarize and
analyze recent work related to interpretable RL with an emphasis on papers published in
the past 10 years. We also discuss briefly some related research areas and point to some
potential promising research directions.


## Introduction

Although combination of deep learning with RL caused a great improvement, it brought its drawback to.
DRL drawbacks :
*  the blackbox nature of deep neural network architectures 
* difficult to train, require a large amount of data
* may overfit  
*  vulnerable to adversarial attacks

##### concerns around non intelligable RL:
1. Ethical concerns
2. Legal concerns
3. Operational concerns
4. Usability concerns

we believe that achieving interpretability in RL should
involve a more encompassing discussion of every component involved in these al-
gorithms, and should stand on three pillars: interpretable inputs (e.g., percepts or
other information provided to the agent), interpretable (transition/reward) models,
and interpretable decision-making (policies or value functions).

we cover additional work that belongs to interpretable
RL such as [[Extras#neuro-symbolic RL]] or [[Extras#relational RL]] and also draw connections to other
work that naturally falls in this designation, such as [[Extras#object-based RL]],[[Overview Extras#physics-based
models]] , or [[Extras#logic-based task]] descriptions.

### Table of contents
1. [[Background]]
2. [[Interpretability and Explainability]]
3. [[Interpretable Inputs]]
4. [[Interpretable Transition and Preference Models]]
5. [[Interpretable Decision-Making]]
6. [[Explainable RL]]
7. [[Future views and our works]]
8. 



