# Sentiment Analysis

## Description

**Sentiment Analysis** is one the most popular tasks in **Natural Language Processing (NLP)**, especially with modern deep learning approaches. In this assignment, we are required to perform sentiment analysis on the VLSP 2016 Dataset using Word2Vec embedding and Neural Network architectures to determine the sentiment of a certain user comment.

## Dataset

- The dataset used to perform sentiment analysis is the **VLSP (Vietnamese Language and Speech Processing)** includes train set and test set with two columns Class and Data corresponding to classified sentiment value in `(-1, 0, 1)` and user comment text.
  - Train: `5100` samples
  - Test: `1050` samples
- More details: [https://vlsp.org.vn/resources-vlsp2016](https://vlsp.org.vn/resources-vlsp2016)

## Preprocess the data

We perform some preprocessing actions on the dataset, including:

- Normalize the text with `underthesea` library, a popular NLP library for processing Vietnamese text data.
- Remove some unnecessary components in text such as URLs, digits, duplicate puctuations, duplicate characters, etc.
- Tokenize the text with Tokenizer from `pyvi` library, another library specialized for Vietnamese text data.

## Build end-to-end model

- We first convert the processed text into numerical vector using a pre-trained **Word2Vec** with **CBOW** embedding model. This model is trained with Vietnamese dataset and provided by our instructor as well. Feel free to use another model that you think it is better.

- We use `tensorflow.keras` library to implement the model layers. After the embedding layer, we concatenate it with three different architectures using:

  1. CNN based
  2. RNN based (LSTM)
  3. Combining of CNN and LSTM

## Train and evaluate

- We perform training on the above architectures, with some addition techniques such as split a validation set, early stopping, etc.

- Finally, we predict on test set and compare the results between three approaches.
