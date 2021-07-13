# Quora-Question-Pair

Semantic Textual Similarity determines the similarity between two samples of text. 

In this project, we determine whether a pair of Quora Questions mean the same or not.

## Step 1: Basic Data Exploratory Analysis

## Step 2: Data Preprocessing

The following steps are performed on each of the sentences-
* Tokenisation
* Puncuation removed
* Replacing numbers
* Replacing stopwords


## Step 3: Identifying semantic units from a sentence

The sentences are divided into smaller parts of a list, where each part is identified based on their
correlation with the parts from the second sentence. The sentence is represented as a word2vec
embedding, and each word is a m-dimensional vector.

## Step 4: Building model and reducing dimension using CCA

In the Word2Vec model, the model matrix has a dimension of V×N, where V is the size of unique
vocabulary and the size of N is the number of neurons in a network. 300 neurons is what Google used in
their published model trained on the Google news dataset. Thus we have 300 dimensions, which is why
we need dimension reduction. CCA is great for scenarios where there are two high dimensional datasets
from the same samples and it enables learning looking at the datasets simultaneously.
By doing CCA, we can identify the common variation, the canonical variates that are highly
correlated to the unknown latent variable.

## Step 5: Cosine Similarity

Cosine similarity between the two vectors is generated, and a custom function is made which
classifies the pair of sentences as duplicate if cosine similarity is greater than 70% (0.7). Else,
they are classified as non-duplicate.
