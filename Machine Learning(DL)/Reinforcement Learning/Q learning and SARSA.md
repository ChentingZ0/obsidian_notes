### Epsilon-Greedy Action Selection
Epsilon-Greedy is a simple method to balance exploration and exploitation by choosing between exploration and exploitation randomly.  

The epsilon-greedy, where epsilon refers to the probability of choosing to explore, exploits most of the time with a small chance of exploring.
![epsilon-greedy](https://media.geeksforgeeks.org/wp-content/uploads/20200318200401/Screenshot-2020-03-18-at-8.03.38-PM.png)
![[Pasted image 20231206145130.png]]

### Q-Learning
![[Pasted image 20231206135351.png]]

- Q-Learning and SARSA are stochastic approximation algorithms
![[Pasted image 20231206140155.png]]

----------------------

**The algorithm**:
![[Pasted image 20231206140830.png]]
$\lambda$  is the discount factor, $\alpha$ is the learning rate. 
![[Pasted image 20231206141705.png]]

--------------------------------------------
### SARSA
![[Pasted image 20231206142116.png]]
![[Pasted image 20231206142715.png]]
![[Pasted image 20231206143031.png]]

