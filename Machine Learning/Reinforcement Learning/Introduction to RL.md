References: 
Chapter1 of Sutton book
Introduction lec and lec4 of CS285

## **RL vs Supervised ML vs Unsupervised ML**

![[Pasted image 20231107140546.png]]
![[Pasted image 20231107140812.png]]
![[Pasted image 20231107141939.png]]

p2:
![[Pasted image 20231107142823.png]]

- **Main elements of Reinforcement learning** P6

 RL: an agent interacts with an environment by following a policy. In each state of the environment, it takes action based on the policy, and as a result, receives a reward and transitions to a new state. The goal of RL is to learn an optimal policy which maximizes the long-term cumulative rewards.

*Policy*, a *reward signal*, a *value function*, a *model* of the environment.
1. Policy: defines the learning agent's way of behaving at a given time. A mapping from perceived states of the environment to actions to be taken when in those states.
2. Reward: at each step, the environment sends to the agent a reward, the agent's objective is to maximize the total reward it receives over the long run.
3. Value function: how good or bad are we, the total amount of reward an agent can expect to accumulate over the future, starting from that state.
4. model: something that mimics the behaviour of the environment.

-------------------------------------------------------------
![[Pasted image 20231107184753.png]]![[Pasted image 20231107184741.png]]
Explanation of $P_{\theta}$
![[Pasted image 20231107184722.png]]


-------------------------------------------------------------
![[Pasted image 20231107185214.png]]

---------------------------------
## Important concepts in RL
![[Pasted image 20231107190612.png]]

![[Pasted image 20231107190750.png]]
*State-value function*: functions of states that estimate how good it is for the agent to be in a given state. The notion "how good" is defined in terms of future rewards that can be expected.(expected return)

*Action-value function*: expected return starting from s, taking the action a under policy $\pi$.

Property: value functions satisfy recursive relationships


![[Pasted image 20231107191039.png]]
![[Pasted image 20231107191039.png]]

### Types of RL algorithms
![[Pasted image 20231107191150.png]]
- **Policy gradients**: directly differentiate the objective
Example: [[Natural policy gradient]], [[Trust region policy optimization]]
- **Value-based**: estimate value function or Q-function of the optimal policy
Example: [[Q-Learning]], [[DQN]] [[Temporal difference learning]], [[Fitted value iteration]]
- **Actor-critic**: estimate value function or Q-function of the current policy, use it to improve policy
Example: [[Asynchronous advantage actor-critic (A3C)]], [[Soft actor-critic (SAC)]]
- **Model-based RL**: estimate the transition model
Example: [[Dynamic programming in MDP]], [[Guided policy search]]

![[Pasted image 20231107191719.png]]
	![[Pasted image 20231107191724.png]]
	![[Pasted image 20231107191734.png]]
## On-Policy vs Off-Policy
- Off policy: able to improve the policy without generating new samples from that policy.
- On policy: each time the policy is changed, even a little bit, we need to generate new samples.

