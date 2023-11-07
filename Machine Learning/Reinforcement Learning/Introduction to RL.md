## CS285 Course structure:
![[Pasted image 20231107135935.png]]


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


