1. [[Interpretable Inputs#Structured Approches||Structured Approaches]]
2. [[Interpretable Inputs#Learning Symbolic Reperesentation||Learning Symbolic Reperesentation]]
3. [[Interpretable Inputs#Hierarchical Approaches|| Hierarchical Approaches]]


### Structured Approches
the MDP is assumed to be structured and the problem is solved within that struc-
ture: task, reward, state transition, policies and value function are dened over
objects and their interactions|e.g. using first-order logic (FOL)  as in RRL.

##### Variations: 
Relational MDP
Relational RL

**Conclusion** In ==structured MDP== and ==relational RL==, by borrowing from symbolic
reasoning, most work leads to agents that can learn and reason about objects. Such
an explicit, logical representation of learned structures ==may help both generalization
or transfer learning eciently and robustly in similar representational frameworks|==
e.g., combinatorial generalization. However, some major drawbacks are that these
approaches necessitate the symbolic representation to be hand-designed, and often
rely on non-dierentiable operations. They are therefore not very 
exible over
framework variations (e.g., task or input) and not well suited for more complex
tasks, or noisy real-life environments.




### Learning Symbolic Reperesentation

When inputs are given as high-dimensional raw data, it seems judicious|although
challenging|to extract explicit symbolic representations on which we can arguably
reason and plan in a more ecient and intelligible way. This process of abstrac-
tion, which is very familiar to human cognition8, reduces the complexity of an
environment to low dimensional, discrete, abstract features. By abstracting away
lower-level details and irrelevant variations, this paradigm brings undeniable ad-
vantage and could greatly leverage the learning and generalization abilities of the
agent. Moreover, it provides the possibility of reusing high-level features through
environments, space and time.

##### variations:
1. Symbol grounding
2. Object-Recognition
3. Relational Representations
**Conclusion** ==Extracting symbolic and relational representations from high dimen-
sional raw data is crucial as it would avoid the need of hand-designing the symbolic
domain, and could therefore unlock enhanced adaptability when facing new envi-
ronments.== Indeed, the symbolic way of representing the environment inherently
benets from its compositional and modular perspective, and enables the complex-
ity of the==state-space to be reduced thanks to abstraction.== Moreover, most of the
modules presented in this section may be conveniently incorporated as a preprocess-
ing step for any object-oriented or relational RL, either being trained beforehand
or more smoothly end-to-end with the subsequent model.



### Hierarchical Approaches

Instead of working entirely within a symbolic structure as in Section 4.1, many
researchers have tried to incorporate elements of symbolic knowledge with sub-
symbolic components, with notable examples within hierarchical RL (HRL, cf.
[106]). Their aim was notably to leverage both symbolic and neural worlds, with a more structured high-level and a more flexible low-level.
Table 3 introduces these
approaches, focusing notably on their high-level interpretability, as their lower-level
components rarely claim to be interpretable. Indeed, dierent levels of temporal
and hierarchical abstractions within human-decision-making arguably participate
to make it more intelligible. For instance, [107] demonstrates how a meta-controller
providing subgoals to a controller leverage both performance and interpretability
for robotic tasks.
##### approaches : 
1. Modularity
2. Symbolic Planning
3. Declarative Domain Knowledge

**Conclusion** Symbolic knowledge and reasoning elements have been consistently in-
corporated to (symbolic) planning or hierarchical decision-making, in models which
may reach a certain high-level interpretability, albeit neglecting action-level inter-
pretability. Moreover, most work still typically relies on manually-crafted symbolic
knowledge|or has to rely on a (pretrained or jointly-trained) perception model for
symbol grounding|assuming a pre-given symbolic structure hand-engineered by a
human expert. Due to the similarities shared by the majority of discrete dynamic
domains, some researchers [115] have argued that a laborious crafting of symbolic
model is not always necessary, as the symbolic formulation could adapt to dierent
problems, by instantiating new types of objects and a few additional rules for each
new task; such claim would still need to be backed by further work in order to
demonstrate such 
exibility. When adopting a symbolic or logical high-level frame-
work, we also have to handle a new trade-o between expressivity and complexity
of the symbolic representation.

