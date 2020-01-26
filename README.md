# Masters-thesis-chatbot
Master Thesis Project: Developed a Chatbot using NLP and RNN 

## Project Overview
The project aims to develop a chatbot which can reply domain-related questions. This project presents an end-to-end sequence to sequence mapping architecture that has been used for machine translation. The model learn the semantic and syntactic relations between the source and target sentence pairs by maximizing the likelihood of the target sentence given the source.

## Datasets
  ### Cornell movie dataset
  This corpus contains a set of 220,579 fictional conversations involving 9035 characters from 617 movies including the meta-data (Danescu-Niculescu-Mizil and Lee, 2011). After pre-processing (removing movie name, character names etc) and limiting the length to less than 20, we got a final set of 139979 conversations. Seq2Seq model with and without attention mechanism is applied on this dataset. 
  Here are the model parameters used:
  * source vocab size 20,000
  * target vocab size 20,000
  * number of layers 2
  * number of hidden neurons in each layer 512
  * learning rate (initial) 0.5
  * learning rate decay factor 0.99
  
  ### TIDES-IIIT parallel Corpus
  The DARPA-TIDES corpus was released as part of language contest on SMT in 2002. After manual refinement and cleaning, a subset of this corpus was released for the NLP Tools Contest (Venkatapathy, 2008) on SMT for English-Hindi. As mentioned in Venkatapathy (2008) "the translations are not faithful. They are paraphrased in such a way that they convey the meaning in the best possible way. i.e they are not the exact translations.". This data set contains 50k training sentences and 1k each for validation and testing (Bojar et al., 2010). Here we limited the sequence length to 30. Hence, any training data that has more than 30 tokens are omitted in our experiments. This made the effective training data of size 33028 and validation data size 716. 
  Following are the model parameters used.
  * English Vocabulary 8k
  * Hindi Vocabulary 8k
  * number of layers 2
  * number of cells in each layer 512
  * sampled softmax with 1024 samples
  * batch size 32

## Base model & Datasets
Seq2Seq model with the attention mechanism has shown significant improvement in the BLEU score of the translation task applied on TIDES-IIIT English-Hindi corpus. But the same model didn't result much change in the perplexity on the cornell movie datset. 

## Setup
Encoder-Decoder LSTM model is being trained with the following model parameters:
  * source sequence size(maximum) = 20
  * target sequence size(maximum) = 5
  * Vocabulary size(Source side) = 400
  * Vocabulary size(Target side) = 200
  * Number of layers = 2
  * Number of neurons (Each layer) = 128
  * Embedding size = 24
  * Learning rate (initial) = 0.5
  * Learning decay rate = 0.99

## Result
This shows that the attention mechanism is useful in learning the alignment between the source and target words in MT task rather than on a mere question-answering task.
