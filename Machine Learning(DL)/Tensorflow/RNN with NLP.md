Natural Language Processing with RNNs
[youtube](https://www.youtube.com/watch?v=tPYj3fFJGjk&t=16880s&ab_channel=freeCodeCamp.org)
### Convert textual data to numeric data
- Bag of words ×
- Integer Encoding ×
- **Word Embedding** √
This method keeps the order of words intact as well as encodes similar words with very similar labels. It attempts to not only encode the frequency and order of words but the meaning of those words in the sentence. It encodes each word as a dense vector that represents its context in the sentence.

For each vector, the dimensions will be *64* or *128*. And every single component of that vector will tell us what group it belongs to or how similar it is to other words.

Word Embedding is actually a layer:
You can add what's called an _embedding layer_ to the beggining of your model and while your model trains your embedding layer will learn the correct embeddings for words. You can also use pretrained embedding layers. 

#### RNN with NLP
Difference between RNN and other neural network: 
It contains an internal loop. A RNN will process one word at a time while maintaining an internal memory of what it's already seen.
**Feed-forward neural networks**: this means our data will not be fed into network at once, is fed forward from left to right.

LSTM: deal with forgetful issues.

### Sentiment Analysis