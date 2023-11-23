[medium](https://medium.com/towards-data-science/transformers-intuitively-and-exhaustively-explained-58a5c5df8dbb)
[StatQuest transformers](https://www.youtube.com/watch?v=zxQyTK8quyY&t=471s&ab_channel=StatQuestwithJoshStarmer)

Pre-requisites: Neural Network, Embeddings, encoders, decoders
### Word Vector Embeddings
Word2Vect, a landmark paper in the natural language processing space.
In essence, a word vector embedding takes individual words and translates them into a vector which somehow represents its meaning.
(Called embedding)
![word-to-vector](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*To16j0huNMboA7FefEaiIQ.png)

- State-of-the-art of word embedding: 
	GloVe, Word2Vec, FastText, Sub-word embedding

### NLP with RNN
Train a neural network that would feed into itself over sequential inputs.
[[RNN with NLP]](one practical example of tensorflow)
- Recurrent networks feed into themselves can be used for sequences of arbitary length.
- Different modeling problems: 
1. Sequence to sequence modeling
	Predicting the next word for text complete
2. Sequence to vector modeling
	Scoring how satisfied a customer was with a review
3. Vector to sequence modeling
	Compressing an image into a vector and asking the model to describe that image as a sequence of text
4. Sequence to vector to sequence modeling.
	 Text translation, where you need to understand a sentence, compress it into some representation, then construct a translation of that compressed representation in a different language.
![modeling](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*cTnlL4DIeWb0Las1bZWUYw.png)

- Each layer shares the same weights it’s easy for recurrent models to forget the content of inputs. As a result, RNNs could only practically be used for very *short sequences of words*.
- Forgettable network!!!
### LSTM
[[LSTM]](General network representation)
Memorable!! Help to improve RNN to recall important information.
![LSTM](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*DcMiCsQXY6HSxDOv7BE7ig.png)
However, while LSTMs could model longer sequences, they were too forgetful for many language modeling tasks.

### Self attention mechanism
It decides which inputs are currently relevant and which are not.

This approach proved to have a massive impact, particularly in translation tasks. It allowed recurrent networks to figure out which information is currently relevant, thus allowing previously unprecedented performance in translation tasks specifically.
![.](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*aLQY6OGtDoATTypz.png)

### The Transformer
Transformer, which used a combination of previously successful and novel ideas to revolutionize natural language processing.
[landmark paper](https://arxiv.org/pdf/1706.03762.pdf)
![diagram](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*QTWF88d36EcIi3bdsb46pA.png)

1. ==**High Level Architecture**==
- Encoder/decoder style model. -> sequence to vector to sequence model
	The encoder takes some input and compresses it to a representation which encodes the meaning of the entire input. The decoder then takes that embedding and recurrently constructs the output.

#### Encoder part
2. ==**Input Embedding and Positional Encoding**==
![.](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*dc7O6IVybmxk4ce_WvPaBg.png)
 - A word space embedder like word2vect converts all input words into a vector embedding. However, unlike recurrent strategies, transformers encode the entire input in one shot. As a result the encoder might lose information about the *location* of words in an input.

~ I like eating Pizza/ Pizza likes eating me QAQ Different!! Location matters!! ~

- To resolve this, transformers also use **positional encoders**, which is a vector encoding information about where a particular word was in the sequence.

- The vector used to encode the position of a word is added to the embedding of that word, creating a vector which contains both information about where that word is in a sentence, and the word itself.
(word embedding + positional information) is what we need!
3. ==**Multi-Headed self Attention**==
The Pizza came out of the oven and it tasted good!
it? -> Pizza or oven ? QAQ -> Self Attention matters!! Similarity score
![diagram](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*zG3V2yLkmjtpbK4xRofcTA.png)
 It’s a “co-relation” and “contextualization” mechanism. It allows words to interact with other words to transform the input (which is a list of embedded vectors for each word) into a matrix which represents the meaning of the entire input.
 ![diagram](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*W0AWU-bmt7RLP-cX32L7sg.png)
 This mechanism can be thought of four individual steps:
 
==3.1 **Creation of the Query, Key, and Value**==
![1](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*9d30Pgi--bKhrg9w2kBTag.png)
![dense](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*9d30Pgi--bKhrg9w2kBTag.png)

==3.2 **Division into multiple heads**==
![multiple head](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*HhefCKgypAyWNDHFkRuHSw.png)


==3.3. **The Attention Head**==

In the attention mechanism the Query and Key are matrix multiplied together to create what I refer to as the “Attention Matrix”.
![attention matrix](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*GPb57rANqqMxG5VbxvByCQ.png)
Now that we have the attention matrix, it can be multiplied by the value matrix.
![multiply](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*_9ppezRIFUXs0XltgzE_nQ.png)
==3.4 **Composing the final output**==

Each of these heads output a different result, which can be concatenated together.
![concatenate](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*9rJv-21-5ogQsUH2LYFNHw.png)

==3.5 **Add and Norm**==
- Skip connections
Example: [[U-Net]] Image segmentation using a U-net architecture
Gradient explosions, rank collapse. -> 
A model can overthink a problem, and as a result it can be useful to re-introduce older data to re-introduce some of that simpler structure.
![skip connection](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*UvEhdbLA3Eb9WWSZMSW1bw.png)

- Layer normalization
 If you do data science on this matrix, you might have to deal with both incredibly small and massively large values.
 
Layer normalization computes the mean and standard deviation (how widely distributed the values are) and uses those values to squash the data back into a reasonable distribution.

==3.6 **Feed Forward==**
![feed forward](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*fqEwpbKj7HIQb1FhjZDlyg.png)
Final final result of all encoder part!!
A projection, where the model can learn how to project the attention output into a format which will be useful for the decoder.

#### Decoder part

![decoder](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*02fitpQsgiTRR7U770g-4Q.png)
Similar to the encoder
- Use the same word to vector embedding approach and employs the same positional encoder. 
- **==Masked multi headed self attention==**
One of the core flaws of recurrent neural networks is that you need to train them sequentially. This makes training RNNs incredibly slow as each sequence in the training set needs to be sequentially fed through the model one by one.
-> careful modifications to the attention mechanism transformers can get around this problem

- Solution: When training a model, you have access to the desired output sequence. As a result, you can feed the entire output sequence to the decoder (including outputs you havent predicted yet) and use a mask to hide them from the model. This allows you to train on all positions of the sequence simultaneously.

![mask](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*OMzbUU_kfKBE1msgFX3ZLg.jpeg)





