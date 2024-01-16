![[Pasted image 20231216184750.png]]

- Two components: actor, critic
The actor takes the current environment state and determine the best action to start from there. Aritic takes the evaluation role by taking the environment state and the action, and returning a score to present how good the action is.

- Actor critic models require much less training time than policy gradient methods.

A combination of value-based and policy-based methods, where the Actor controls how our agent behaves using the Policy gradient and the Critic evaluates how good the action taken by the Agent based on value-function.

## Basic model
[medium](https://arshren.medium.com/unlocking-the-secrets-of-actor-critic-reinforcement-learning-a-beginners-guide-3c5953b13551)

![actor-critic](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*CvqcmE569aBSfo4W5tu22g.png)

The Actor-Critic algorithm takes inputs from the environment and uses those states to determine the optimal actions.

The Actor component of the algorithm takes the current state as input from the environment. It uses a neural network, which serves as the policy, to ==output the probabilities of each action for the state==.

The Critic network takes the current state and the Actor’s outputted actions as inputs and uses this information to estimate the expected future reward, also known as the Q-value. The Q-value represents the expected cumulative reward an agent can expect to receive if it follows a certain policy in a given state.

On the other hand, the value state represents the expected future reward for a given state, regardless of the action taken. It is calculated as the average of all the Q-values for a given state over all possible actions.

**The difference between the expected reward and the average reward for the action is referred to as the advantage function or** **temporal difference**

#### Adv. = Q(s,a) — V(s)

The advantage function provides valuable information to guide the Actor’s policy, allowing it to determine which actions will lead to the best outcomes and adjust its policy accordingly.

- If the advantage function for a particular state-action pair is positive, taking that action in that state is expected to yield a better outcome than the average action taken in that state.

- The negative value of the advantage function indicates that the current action is less advantageous than expected, and the agent needs to explore other actions or update the policy to improve the performance.

As a result, the advantage function is backpropagated to both the Actor and the Critic, allowing both components to continuously update and improve their respective functions. This results in improved overall performance, as the Actor becomes more effective at making decisions that lead to better outcomes. Ultimately, the Actor-Critic algorithm learns an optimal policy that maximizes the expected future rewards.

## Code Implementation
![figure](https://miro.medium.com/v2/resize:fit:828/format:webp/1*bTlZitGuWB-yWRFGBdijKg.png)
Code in the essay.

- A2C algorithm

- DDPG