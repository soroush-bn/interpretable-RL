

## neuro-symbolic RL
	todo


## relational RL



![[1_4ksW1jcA4OXtoxx7EkKMQA.webp]]

# How Relational block work?

Looking at the structure of the model. First, an image of size (batch, 64, 64, 3) is passed through two CNN. In this way, a matrix of size (batch, W, H, C) is obtained. If this is converted to size (batch, W x H, C), then a number of W x H entities that has a number of C feature is obtained.


![[1_I-jfooRsAwMH-nuo3ii6kQ 1.webp]]
The following is to put the previously obtained (batch, W x H, C) size entity into the MultiHeadAttention model as query, key, and value. This will also yield an attention value of size (batch, W x H, C).



![[1_DReYBMIerb7QS-ixScSJUg.webp]]


Finally, add the entity with the size of (batch, W x H, C) with attention. Then, select the entity with the maximum C value. It will give a matrix of size (batch, C). Applying dropout to the attention value before residual operation and then layer normalization after the operation.
![[1_Ryjrqef1mFb9M5crWUeVsg.webp]]




The following is to put the previously obtained (batch, W x H, C) size entity into the MultiHeadAttention model as query, key, and value. This will also yield an attention value of size (batch, W x H, C).




![[1_DReYBMIerb7QS-ixScSJUg 1.webp]]

Then, the resulting value can be used as a common feature in Deep Reinforcement Learning.

![[1_-uVZGTX0bbozyUZ-q6S1Jw.webp]]



## DSRL




## Hierarchical Reinforcement Learning



-   mproved exploration: thanks to the use of high-level actions, the action space is reduced and exploration is simpler.
-   Sample efficiency: states can also be managed in a hierarchical way, and low-level policies can hide irrelevant information from its higher-level policies. This reduces the state space too, which improves sample efficiency as I explained before.
-   Transfer learning: sub-policies, or low-level policies, can be re-used for different tasks. Let’s say an agent learnt how to make coffee but now you want it to learn how to make a cappuccino, if you split the task of making a cappuccino in making coffee and then warming up milk and making it foamy, then the first robot can already use its experience for making the coffee, which will accelerate learning for this new task.
#### The Options Framework

The Options Framework, introduced by [Sutton, Precup & Singh in 1999](http://papers.nips.cc/paper/1586-learning-macro-actions-in-reinforcement-learning.pdf), provides a way to implement hierarchies and macro-actions in RL. This is probably one of the most common formulations of HRL.

In the Options Framework, the agent is in a Semi-Markov Decision Process (SMDP), an extension of Markov Decision Processes in which the time between actions is not constant, allowing it to include different levels of abstractions for its actions.

The Options Framework introduces the concept of **option**, a generalization of an action that lets us introduce macro-actions. An example of an option could be picking up an object (which involves certain muscle twitches), but it could also be one single muscle twitch. In these two examples, the first one is a macro-action formed by multiple primitive actions, while the second one is a primitive action. [Sutton et al. (1999)](https://pdf.sciencedirectassets.com/271585/1-s2.0-S0004370200X00549/1-s2.0-S0004370299000521/main.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjEIP%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJGMEQCIESLGtl5GrhhtZzdj5yqOgLrGDYmpVYXrKly71u0oGyFAiBv%2FCP50jyEYbf%2F%2BE2HfV6EW7K5zBrv5JIzFhq9uCH6Eyq9Awi8%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F8BEAMaDDA1OTAwMzU0Njg2NSIMNYyrwvB33DZ1Kvq2KpED2FGegHwZmRk4sG7jfW1H78WdCz2G5%2BpEUrTz7aVuPOz0Zq0uPgCvB%2FKt%2FnIs0nxyfjamVx%2BTiEg7mXd8Kx7LV1EuFqSrFAIZnICMr5wmQowQ5D1XY%2BGCRRCgAsSi2BYqPtVpR6taAMgOwvaotyUXU0l6%2BVWE%2F5WJJEYkKdSYNhFGTLGwt0q7KtzO4B8n1BydcHuoeUmAfXptKjAQ8UFMEC2UnQNcBEz3tsN1SnC7%2BGvMi79YSxGypwzqa6SjZK1AyUQMRi%2F8whfXBereqN3ambFtnW0uGU9iuZi3MXWC3oZVQkrEmvXrqFeb21V0XZhprRG9NzDdpDmCrtuWWJsDu8XJTR8978wWKmHFPfnOMdQ6DvJ12vfy%2BwxNktNdVe8Tv61CwpYaHVU1n0D9h7VnGYjrA00XwBbdSd1HWv%2BTf88TMfRfHWi1emigaIsCFO8roZA8NOtsagNpLnKUuTrh89c1SeNGHrkyp9bKiEAe4Lztujruty1HSYm%2Bel0wUKdfpL4F%2FH7BtEHgq9bEwSiYrGYw3MzP9QU67AGxunsKSQrJkq6nGSSjWdrUrWMcvcBN6YtyOo7S5Ou%2F5s4WeZltWSkYMKa%2FbrbnLbNwvk%2BmMYUEfroS%2FNN51aaY03WfncGwo6DvX6S3llWno0E5mtLiF7x3JYXkilFnXnpcleWERzSP6ubqMLFYxyvsFAdgImdAK4DXxV89kmyht0tG%2FxQeQ1BULxqwbg8RlTIL0TTusUvCDy8Wu0zaRJpwxvwYZAWukK7VbnrGEkMZkaJ7iVs9EZBgMmw72HW7sRViY2X3qdfbJCI4Twzbx1T%2FXwhJ8RH50e0LpE%2B5CXwZIc5iHqee3pw5E7mWfA%3D%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20200507T112434Z&X-Amz-SignedHeaders=host&X-Amz-Expires=299&X-Amz-Credential=ASIAQ3PHCVTY2WMI6KVY%2F20200507%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=fbeea06d2fffc09501375dfd3c8ccb28725cbffa5f2776ac31e8fb35278d5d0a&hash=e3cf3d3e59d1e679b1771c52c7242cfd07f5faa8a499adb416f226a1b1297e89&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=S0004370299000521&tid=spdf-d8bd98f6-5625-46bc-b78e-9f168d0a531b&sid=2d141b7d833611469889b85080d0b045cbe8gxrqb&type=client) introduce the concept of options and describe them like this:

> Options consist of three components: a policy π : S × A → [0, 1], a termination condition β : S+ → [0, 1], and an initiation set I ⊆ S. An option ⟨I,π,β⟩ is available in state st if and only if st∈ I. If the option is taken, then actions are selected according to π until the option terminates stochastically according to β.

This means that each time a new state is observed, the initiation set I is checked to see if the current state belongs to it, if so, the option starts: from now on, π determines the action to take in each step (instead of the global policy) and in each state, the termination condition β is checked, if the it returns True, then the option finishes and we’re back to using the global policy. In the image below, we can see how using options lets us manage actions and states with different temporal lengths.


![[1_IZSMiPG7UMfYBNtBeMKp4w.webp]]https://thegradient.pub/the-promise-of-hierarchical-reinforcement-learning/
