References: 
(lec4 of KTH slides, Chapter 567 of Sutton's book)

Discounted Return vs. State Value Function
![return](https://miro.medium.com/v2/resize:fit:828/format:webp/0*Mx-nOpbgmkXDoKmO.png)
## Monte Carlo methods
Different from Dynamic programming, 
Monte Carlo method on the other hand is a very simple concept where agent learn about the states and reward when it interacts with the environment. In this method agent generate experienced samples and then based on average return, value is calculated for a state or state-action

Evaluate policies through sampling. Monte Carlo methods require only experience, there is no model(agent does not know state MDP transitions). 

Monte Carlo methods only for episodic tasks. Monte Carlo methods can be incremental in an episode-by-episode sense. Only after a cmplete episode, values are updated.

There is no bootstrapping

- Analogy: Monte Carlo learning is like annual examination where student completes its episode at the end of the year. Here, the result of the annual exam is like the return obtained by the student.
- Example:

![total reward](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*8H_U9U2SYes8MhlA.png)

Return(Sample 01) = 2 + 1 + 2 + 2 + 1 + 5 = 13 gems
Return(Sample 02) = 2 + 3 + 1 + 3 + 1 + 5 = 15 gems
Return(Sample 03) = 2 + 3 + 1 + 3 + 1 + 5 = 15 gems
Observed mean return (based on 3 samples) = (13 + 15 + 15)/3 = 14.33 gems
Thus state value as per Monte Carlo Method, $V_{\pi}(S_{05})$ is 14.33 gems based on 3 samples following policy π.


### Monte Carlo Backup diagram
![backup diagram](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*_BZ7de2MQZHLUGud.png)

### First Visit Monte Carlo Method
In this case in an episode first visit of the state is counted (even if agent comes-back to the same state multiple time in the episode, only first visit will be counted)
![first visit Monte Carlo](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*7OfkMiUYKF-YehrC.png)

### Every Visit Monte Carlo Method
In this case in an episode every visit of the state is counted.
![every visit Monte Carlo](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*dzOaC4UyiB_X0Vf2.png)


## Stochastic approximation algorithms
Robbins-Monro Algorithm
Stochastic Approximation is a family of model-free stochastic algorithms
![[Pasted image 20231108200315.png]]
![[Pasted image 20231108200832.png]]


