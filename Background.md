The success of deep RL is explained partly by the use of neural networks to
approximate value functions or policies, but also by various algorithmic progress.
Deep RL algorithms can be categorized in two main categories: value-based methods
and policy gradient methods, in particular in their actor-critic version. For the rst
category, the model-free methods are usually variations of the DQN algorithm [28].
For the second one, the current state-of-the-art model-free methods are PPO [29] for
learning a stochastic policy, TD3 [30] for learning a deterministic policy, and SAC
 for entropy-regularized learning of a stochastic policy. Model-based methods
can span from simple approaches such as rst learning a model and then applying a
model-free algorithm using the learned model as a simulator, to more sophisticated
methods that leverage the learned model to accelerate solving an RL problem 

For complex decision-making tasks, hierarchical RL (HRL) [35] has been pro-
posed to exploit temporal and hierarchical abstractions, which may facilitate learn-
ing and transfer, but also promote intelligibility. Although various architectures
have been proposed, decisions in HRL are usually made at (at least) two levels. In
the most popular framework, a higher-level controller (also called meta-controller)
chooses temporally-extended macro-actions (also called options), while a lower-level
controller chooses the primitive actions. Intuitively, an option can be understood as
a policy with some starting and ending conditions. When it is known, it directly cor-
responds to the policy applied by the lower-level controller. An option can also be
interpreted as a subgoal chosen by the meta-controller for the lower-level controller
to reach.