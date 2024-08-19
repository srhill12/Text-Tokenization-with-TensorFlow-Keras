
# Text Tokenization with TensorFlow Keras

This project demonstrates how to tokenize text data using TensorFlow's Keras API. The process involves converting sentences into sequences of integers, where each integer corresponds to a word in the vocabulary.

## Table of Contents
- [Dependencies](#dependencies)
- [Text Tokenization](#text-tokenization)
- [Word Index Mapping](#word-index-mapping)
- [Encoding Text Sequences](#encoding-text-sequences)
- [Regenerating Sentences](#regenerating-sentences)
- [Conclusion](#conclusion)

## Dependencies

To run the code in this project, you'll need to install the following Python libraries:

- [TensorFlow](https://www.tensorflow.org/)

You can install TensorFlow using pip:

```bash
pip install tensorflow
```

## Text Tokenization

We start by defining a list of sentences that we want to tokenize. The Keras `Tokenizer` is used to convert the text into sequences of integers.

### Code:
```python
from tensorflow.keras.preprocessing.text import Tokenizer

sentences = ["I love my dog.", "I love my family.", "My dog is a lab"]
tokenizer = Tokenizer()
tokenizer.fit_on_texts(sentences)
```

## Word Index Mapping

After fitting the tokenizer on the text, we can view the dictionary mapping of words to their respective indices.

### Code:
```python
print(tokenizer.word_index)
```

### Output:
```python
{'my': 1, 'i': 2, 'love': 3, 'dog': 4, 'family': 5, 'is': 6, 'a': 7, 'lab': 8}
```

## Encoding Text Sequences

The next step is to encode each word in the sentences into their corresponding indices, creating a sequence of numbers.

### Code:
```python
sequences = tokenizer.texts_to_sequences(sentences)
print(sequences)
```

### Output:
```python
[[2, 3, 1, 4], [2, 3, 1, 5], [1, 4, 6, 7, 8]]
```

## Regenerating Sentences

Finally, we can regenerate the original sentences from the encoded sequences using the `sequences_to_texts_generator` function.

### Code:
```python
[sequence for sequence in tokenizer.sequences_to_texts_generator(sequences)]
```

### Output:
```python
['i love my dog', 'i love my family', 'my dog is a lab']
```

## Conclusion

This project provides a simple demonstration of how to tokenize text data using TensorFlow's Keras API. The process involves creating a tokenizer, fitting it on text data, and converting the text into sequences of integers. Additionally, the original text can be regenerated from the encoded sequences, which is useful for various NLP tasks.
