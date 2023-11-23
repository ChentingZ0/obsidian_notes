Supervised learning of behaviours
![[Pasted image 20231107152144.png]]
$\pi$ denotes the policy, $\theta$ denotes the parameters

Bayesian Network: 
![[Pasted image 20231107152607.png]]
(Markov property)


### Imitation learning
[medium](https://smartlabai.medium.com/a-brief-overview-of-imitation-learning-8a8a75c44a9c)
In IL instead of trying to learn from the sparse rewards or manually specifying a reward function, an expert provides us with a set of demonstrations. The agent then tries to learn the optimal policy by following, imitating the expert’s decisions.

Generally, imitation learning is useful when it is easier for an expert to demonstrate the desired behaviour rather than to specify a reward function which would generate the same behaviour or to directly learn the policy.

MDP: environment of IL
**_S_** set of states, an **_A_** set of actions, a **_P(s’|s,a)_** transition model, **_R(s,a)_** reward function. The agent performs different actions in this environment based on its **_π_** policy. 

We also have the expert’s demonstrations (which are also known as trajectories) **_τ = (s0, a0, s1, a1, …)_ ,** where the actions are based on the expert’s (“optimal”) **_π*_** policy.

### Behavioural Cloning (BC)
Learning the expert’s policy using supervised learning.(first example in 1989, autonomous driving)
![.](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*sjnBZahPnhPF-EaW.png)

Problems:
Assumption that state-action pairs are distributed: in MDP an action in a given state induces the next state, which breaks the previous assumption.

Errors made in different states add up and may lead to catastrophic failures.

### Direct Policy Learning
An improved version of behavioural cloning.
We roll out our learned policy in our environment, and we query the expert to evaluate the roll-out trajectory.  In each iteration, we collect trajectories by rolling out the current policy (which we obtained in the previous iteration) and using these we estimate the state distribution. Then, for every state, we collect feedback from the expert (what would have he done in the same state). Finally, we train a new policy using this feedback.

![diagram](https://miro.medium.com/v2/resize:fit:720/format:webp/0*yfAgeqJtgI8eGE-O.png)
**Data Aggregation** and **Policy Aggregation** are used to help algorithms to use all previous training data such that the agent "remembers" all mistakes it made in the past.

