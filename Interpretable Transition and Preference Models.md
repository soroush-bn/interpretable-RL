In this section, we overview the work that focuses on exploiting an interpretable
model of the environment or task. This model can take the form of a transition
model (Section 5.1) or preference model (Section 5.2). Such interpretable mod-
els can help an RL agent reason about its decision-making, but also help humans
understand and explain its decision-making. As such, they can be used in an in-
terpretable RL algorithm, but also in a post-hoc procedure to explain the agent's
decision-making. Note that those models may be learned, or not, and, when not
learned, may possibly be fully provided to the RL agent or not. For instance, the
reward function, which is one typical way of dening the preference model, is gen-
erally specied by the system designer in order to guide the RL agent to learn and
perform a specic task. This function is usually not learned directly by the RL
agent (except in inverse RL, [125]), but still has to be intelligible in some sense,
otherwise the agent's decision-making may be based on spurious reasons and the
agent may not accomplish the desired task since a non-intelligible reward function
is hard to verify and may be incorrectly specied.


## Transition Model




## Preference Model


