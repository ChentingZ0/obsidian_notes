### Long Short-Term Memory
A type of Recurrent Neural Networks that is designed to avoid exploding vanishing gradient problem.
(A stepping stone to learn about Transformers)
![[Pasted image 20231030172918.png]]
- Long short-Term Memory uses two separate paths to make predictions about tomorrow. One path is for Long-Term Memories, and one is for Short-Term Memories.
- Long Short-Term Memory uses Sigmoid Activation Functions and Tanh Activation Functions.
![[Pasted image 20231030173358.png]]

### How a unit goes
- Green line that runs all the way across the top of the unit is called the **Cell State** and represents the **Long-Term Memory**. 
  The lack of Weights allows the Long-Term Memories to flow through a series of unrolled units without causing the gradient to explode or vanish.
- The pink line, called the **Hidden State**, represents the **Short-Term Memories**. The Short-Term memories are directly connected to Weights that can modify them.
- The first stage in the Long Short-Term Memory unit determines what percentage of the previous Long-Term Memory is remembered. It is usually called the **Forget Gate**.
- **Input Gate** -> the first three blocks to generate the new Long-Term Memory.
- **Output Gate** -> the last two blocks to produce the final result (0.98 in this example). Formulate the short term memory for the next iteration.
- The **Sigmoid Activation Functions** always play as a role to produce the percentage, while the **tanh Functions** always play as a role to produce the potential Long/Short-Term memory.
![[Pasted image 20231030175841.png]]
![e](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*2pRNV41f80psJ4YvuXm22Q.jpeg)

### Example
#### Predict the prices of stock market
We can unroll them more times to accommodate longer sequences of input data than a vanilla Recurrent Neural Network.
![[Pasted image 20231030180933.png]]
