[Medium](https://medium.com/@shaikhrayyan123/a-comprehensive-guide-to-understanding-bert-from-beginners-to-advanced-2379699e2b51)
**BERT**: Bidirectional Encoder Representations from Transformers.
### Why revolutionized?
It represents a shift in how machines comprehend language, enabling them to understand the intricate nuances and *contextual dependencies*. 

BERT understands the context-driven relationship between words plays a pivotal role in deriving meaning. 

It captures the essence of bidirectionality, allowing it to consider the complete context surrounding each word. It's a paradigm shift in how machines comprehend the essence of human language.

Powered by Transformers which incorporates "self-attention", allowing BERT to weigh the significance of each word based on its context, both preceding and succeeding. 

- Example: 
"The lead singer will lead the band" -> traditional model might struggle with the ambiguity of 'lead'. BERT can distinguish the first 'lead' is noun, while the second is verb. 

### Preprocessing Text for BERT
![mask](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*Wpm5X7kf6CZrAWuI7WyYqw.png)

BERT uses WordPiece tokenization
- WordPiece vocabulary: subwords. It uses WordPiece tokenization to break down words into subwords. Useful for handling long and complex words.


We add special tokes like $[CLS]$ (classification) at the beginning and $[SEP]$ (separation) between sentences.

We also assign segment embedding to tell BERT which tokens belong to which sentence.
- Example: Original Text: “ChatGPT is fascinating.” Formatted Tokens: $[“[CLS]”, “Chat”, “##G”, “##PT”, “is”, “fascinating”, “.”, “[SEP]”]$
```python
from transformers import BertTokenizer  
  
tokenizer = BertTokenizer.from_pretrained('bert-base-uncased')  
text = "BERT preprocessing is essential."  
tokens = tokenizer.tokenize(text)  
  
print(tokens)
```
#### Masked Language Model(MLM) Objective
Some words are masked, which made BERT learns to predict those words from their context. By guessing the missing words, BERT learns how words relate to each other, achieving its contextual brilliance.


### Fine-tuning BERT for specific tasks
![fine-tune BERT](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*-LA8h0eXRZKlzFvrxtsm2w.jpeg)

#### Transfer Learning in NLP
Build on Pretrained Knowledge. Leveraging BERT's pre-existing knowledge and tailoring it for a particular task.

#### Downstream Tasks and Fine-Tuning:
fine-tune BERT -> downstream tasks
Fine-tuning involves updating BERT’s weights using task-specific data
- Examples: sentiment analysis, named entity recognition


### BERT's Training Process
- Pretraining phase
- Masked Language Model(MLM) ojective
- Next Sentence Prediction(NSP) objective
	BERT doesn't understand words, it grasps the flow of sentences. In the NSP objective, BERT is trained to predict if one sentence follows another in a text pair. This helps BERT comprehend the logical connections between sentences, making it a master at understanding paragraphs and longer texts.

BERT’s training process is like teaching it the rules of language through a mix of fill-in-the-blanks and sentence-pair understanding exercises.


#### Word Embedding vs Contextual Word Embeddings
BERT creates different embeddings for the same word based on its context in a sentence.

#### Handling Out-of-Vocabulary(OOV) Words: Taming the Unknown
BERT's vocabulary isn't infinite, so it can encounter words it doesn't recognize. 
1. split into subwords using WordPiece tokenization
2. replace with a special toke,$[UNK]$ unknown

#### Domain Adaption with BERT
Domain adaptation involves fine-tuning BERT on domain-specific data. By exposing BERT to domain-specific text, it learns to understand the unique language patterns of that domain.


#### Knowledge Distillation from BERT
Knowledge distillation involves training a smaller model (student) to mimic the behavior of a larger, pre-trained model (teacher) like BERT.

This compact model learns not just the teacher’s predictions but also its confidence and reasoning.

### Recent Developments
- RoBERTa: better clever
- ALBERT: A Lite BERT
- DistilBERT: Compact, distilled version
- ELECTRA

### BERT for Sequence-to-Sequence Tasks
- Text summarization: condensing Information
- Language Translation