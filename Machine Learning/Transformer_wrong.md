ChatGPT is based on something called a Transformer.
- The first thing is to find a way to turn the input and output words into numbers -> For neural networks, **word embedding**.
- Token -> each word, and <EOS> symbols.


- Regardless of how long the input sentence is, we copy and use the exact same Word Embedding network for each word or symbol.
- All of these Weights are optimized using Backpropagation one-step-at-a-time in the training process.

![[5979d718ac4ada0cb47daea1f721255 2.png]]
