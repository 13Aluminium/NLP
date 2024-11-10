# WEEK 7 : Distributional Semantics
## 1. Distributional Semantics

Distributional semantics is based on the idea that a word's meaning can be understood by the contexts in which it appears. This approach derives word meanings from large text corpora, analyzing the co-occurrence patterns of words. It relies on mathematical and statistical techniques to represent words as vectors in a high-dimensional space, capturing their semantic relationships.

## 2. Distributional Hypothesis

The distributional hypothesis is famously summarized as: "You shall know a word by the company it keeps." This hypothesis, proposed by linguists such as Zellig Harris and John Firth, suggests that words that appear in similar contexts have similar meanings. For example, the words "dog" and "cat" may have similar meanings because they often appear in similar contexts (e.g., "pet," "animal," "fur," etc.).

Example: If we frequently see the words "coffee" and "tea" in similar contexts, such as in phrases like "drink coffee" and "drink tea," distributional semantics will infer that "coffee" and "tea" are semantically related.

## 3. Vector Space Models for Word Representation

In vector space models (VSMs), words are represented as vectors in a high-dimensional space, where each dimension captures certain aspects of a word's meaning based on its context. VSMs rely on the idea that words with similar meanings have similar vector representations.

### Types of VSMs:

    Count-based VSMs: Measure word meaning based on the frequency of words appearing in contexts, using techniques like term frequency (TF) or term frequency-inverse document frequency (TF-IDF).
    Predictive VSMs: Use neural networks to predict words based on context, leading to more sophisticated representations (e.g., Word2Vec).

Example: In a VSM, words like "king" and "queen" may have vectors that are close to each other, representing their semantic similarity.

## 4. Word Embeddings: Word2Vec and GloVe

Word embeddings are dense vector representations of words learned from large text corpora. Unlike traditional VSMs, which may have thousands of sparse dimensions, word embeddings represent words in a low-dimensional, dense space, which captures semantic information more effectively.

**Word2Vec**: A neural network-based model developed by Google. Word2Vec has two main architectures:

    Skip-gram: Predicts the context words given a target word.
    Continuous Bag of Words (CBOW): Predicts the target word based on surrounding context words. Word2Vec captures complex semantic relationships between words. For example, it can learn analogies like: "king - man + woman ≈ queen".

 **GloVe (Global Vectors):** Developed by Stanford, GloVe is a count-based model that combines aspects of both count-based and predictive approaches. It learns embeddings by factoring the co-occurrence matrix of words. GloVe is effective in capturing global statistical information of a corpus, providing robust word embeddings.

**Example of Analogy:**
 With Word2Vec or GloVe embeddings, the vector operation "king - man + woman" results in a vector close to "queen" in the embedding space.

## 5. Contextualized Word Representations: BERT, ELMo, GPT

Traditional embeddings like Word2Vec and GloVe are context-independent, meaning they assign a single embedding for each word. However, words often have different meanings based on context (e.g., "bank" in "river bank" vs. "financial bank"). Contextualized word representations address this by generating embeddings based on the context in which the word appears.

**ELMo (Embeddings from Language Models)**: ELMo (Embeddings from Language Models): ELMo uses deep bidirectional LSTMs to create word representations based on context. It generates embeddings dynamically, depending on the entire sentence.

**BERT (Bidirectional Encoder Representations from Transformers):** BERT is a transformer-based model that captures context from both directions (left-to-right and right-to-left) in a sentence. It uses a masked language model (MLM) approach, where some words are masked, and the model learns to predict these masked words. BERT provides strong contextualized embeddings, handling polysemy (multiple meanings of a word) effectively.

**GPT (Generative Pre-trained Transformer)**: GPT, unlike BERT, is a unidirectional model that generates embeddings based on left-to-right context. While initially designed for generating text, it can also be used to create contextualized representations.

Example: For the word "bank" in the sentences "I went to the bank to withdraw **money**" and "The boat is near the river bank," contextualized models like BERT generate different embeddings based on the context, understanding that "bank" has two distinct meanings.

### 6. Measuring Word Similarity and Word Analogies

Using word embeddings, we can measure word similarity by calculating the cosine similarity between word vectors. Words that have similar meanings (like "car" and "vehicle") will have high cosine similarity, while unrelated words (like "car" and "banana") will have low similarity.

**Cosine Similarity**: Measures the cosine of the angle between two vectors. If the cosine similarity is close to 1, the vectors are similar.

**Example of Word Analogy:**

    The analogy "man : king :: woman : queen" can be expressed using vector arithmetic: "king - man + woman ≈ queen." By performing this operation, we can find analogous relationships in the embedding space.

## 7. Applications of Distributional Semantics

Distributional semantics has many applications in NLP, such as:

**Word Clustering:** Grouping words that have similar meanings or are used in similar contexts. This can be useful in tasks like topic modeling or document clustering.

**Synonym Detection**: Finding words with similar meanings. For instance, words like "happy" and "joyful" can be identified as synonyms using word embeddings.

**Sentiment Analysis**: Word embeddings help capture nuanced meaning and context, which can be essential for understanding the sentiment in sentences.

**Machine Translation**: Distributional semantics helps in mapping words with similar meanings across languages, improving translation quality.
