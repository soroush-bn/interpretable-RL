
### definition
interprebility : we simply understand interpretability as a ==passive quality of a
model==, while explainability here refers to an active notion that corresponds to any
external, usually ==post-hoc==, methodology or proxy aiming at providing insights into
the working and decisions of a trained model, although both notions are epistemo-
logically inseparable from both the observer and the context.

While the former approach is achieved by ==resorting to more transparent models==,
the latter approach is carrying out ==additional processing steps== to explicitly provide a
kind of explanation aiming to clarify, justify, or rationalize the decisions of a trained
black-box model.


interprebality -> understanding the mechanics of the model 
explainability -> functional understanding (often model-agnostic) of outcome of a model 

![[Pasted image 20230322102957.png]]

Fig. 2: Illustrations of the dierent approaches for interpretable inputs: (Left)
Structured Approach, (Center) Extracting Symbolic Representation, (Right)
Hierarchical Approach. Dashed lines represent optional links, depending on
the methods.




#### how we define algorithmic transparency ? 

with 3 terms as follow :
	1. A model is simulatable if its inner working can be simulated by a human. Ex-
amples of simulatable models are small linear models or decision trees.
	2.  A model is decomposable if each of its parts (input, parameter, and
calculation) can be understood intuitively.
	3.an algorithm is transparent if its properties are well-understood (e.g., convergence).



### interpretability in RL

For this whole process to be interpretable, all its components have arguably to
be intelligible, such as: (1) the inputs (e.g., observations or any other information
the agent may receive) and its processing, (2) the transition and preference models,
and (3) the decision-making model (e.g., policy and value functions).