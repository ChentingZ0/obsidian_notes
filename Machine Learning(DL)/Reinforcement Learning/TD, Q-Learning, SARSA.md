For Monte Carlo updating rule:
Monte Carlo methods update the value of a state only after the reward is returned (only at the end of the episode Gt is known).
![monte update](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*ZVXp3P_31FmrAJj-eHSPUA.png)

## TD(Temporal-Difference) learning methods
- A blend of the Monte Carlo method and the Dynamic Programming method. Similarly to Monte Carlo methods, TD methods can work in a model-free learning. Similarly to DP, TD methods update the value estimates based partially on other estimates, without having to go through the entire episode (they bootstrap).

TD learning is like updating value in every time step and does not require wait till end of episode to update the values
1. There is no model (the agent does not know state MDP transitions)
2. the agent **learns** from **sampled** experience (Similar to MC)
3. Like DP, TD methods update estimates based in part on other **learned estimates**, without waiting for a final outcome (they **bootstrap** like DP).
4. It can learn from **incomplete episode** thus this method can be used in continuous problems as well
5. TD updates a guess towards a guess and revise the guess based on real experience


- Analogy: TD Learning can be thought like a weekly or monthly examination (student can adjust their performance based on this score (reward received) after every small interval and final score is accumulation of the all weekly tests (total rewards)).


### TD(0)
Compared to Monte Carlo updating rule, TD method only need to wait until the next time step to create an update using the observed reward Rt+1 and the estimate V (St+1).

The algorithm is illustrated as follows:
We have α as a learning factor, γ as a discount factor. 
![book](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*XgYfwtziyensbe3xLN0XUA.png)
![TD](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*LBzjmR-JJuofWUyWWJ-Txw.png)
Backup diagram:
![backup](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*uYvVjE__r4tsAz8E.png)
### SARSA
One of the TD algorithms for **control or improvement** is SARSA
Name: agent takes one step from one state-action value pair to another state-action value pair and along the way collect reward R.
$S_{t}, A_{t}, R_{t+1}, S_{t+1}, A_{t+1}$ tuple that creates the term **S,A,R,S,A**

SARSA is an **on-policy** method. It uses action-value function Q and follow the policy $\pi$. 

The algorithm is illustrated as follows:
![book](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*D0IYuvz36Gefp4wTmhPV7g.png)
![SARSA](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*eEEOhaWLP3k-YgbGpXquXg.png)
![backup](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*eCxNf0x_6EQbrL-2.png)
### Q-learning
Q-learning is an **off-policy** algorithm. Q-learning is very similar to Sarsa, except that in the update stage of Q(S,A), we take the maximum over next state-action pairs.

In Off-policy learning, we evaluate target policy (π) while following another policy called **behavior policy** (μ). In the Q-learning, target policy is a **greedy policy** and behavior policy is the **ε-greedy policy**

The algorithm is illustrated as follows:
![book](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*EnRhlXdsJ_1DFyaweS33bQ.png)
![Q learning](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*5jl8JLDcmQnQaCOvjqK0Bg.png)

### Expected Sarsa
Expected Sarsa is very similar to Q learning, except that instead of taking the maximum over next state–action pairs it uses the expected value, considering the probability of each action to happened in the policy
![algorithm](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*G6zfa6FfJu1tMq88DU-iQQ.png)

- **Backup diagram** : Q-learning vs Expected Sarsa
![backup](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*ULfyFsED8LLjYrpzXj_d6w.png)

