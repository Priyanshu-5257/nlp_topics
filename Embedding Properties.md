### 1. Cosine Similarity (High-Frequency)

When words are mapped to dense vectors in a high-dimensional space, we need a mathematical way to determine how "close" or similar two words are. Cosine similarity is the absolute standard for this.

- **How it works:** It measures the cosine of the angle between two vectors. It specifically ignores the _magnitude_ (length) of the vectors and only cares about their _direction_.
- **Expression:** $\text{Cosine Similarity} = \frac{A \cdot B}{||A|| \times ||B||}$ (The dot product of vectors A and B, divided by the product of their magnitudes).
- **Why it's used:** It returns a value between -1 and 1. A score of 1 means the vectors point in the exact same direction (highly similar words), 0 means they are orthogonal (unrelated), and -1 means they point in exactly opposite directions. Because it ignores magnitude, a word that appears frequently (long vector) can still be perfectly similar to a rare word (short vector) if they share the same context.

### 2. Nearest Neighbor Search

Once you have computed embeddings, you often want to find the most similar words to a target word.

- **How it works:** You take the vector of your target word and calculate the distance (usually using cosine similarity) to _every other word vector_ in your vocabulary to find the closest matches (the K-Nearest Neighbors).
- **The Challenge:** In modern systems with millions of vectors, doing a brute-force exact search is too slow. Therefore, **Approximate Nearest Neighbor (ANN)** algorithms (like FAISS or HNSW) are often used to rapidly query and find the closest vectors in logarithmic time.

### 3. Bias in Embeddings (High-Frequency)

Word embeddings learn from massive corpora of human text (like Wikipedia or Common Crawl), meaning they inevitably absorb and amplify the human biases present in that text.

- **How it manifests:** The geometry of the vector space will reflect stereotypes. A famous paper demonstrated that if you ask a Word2Vec model to solve the analogy `"Man is to Computer Programmer as Woman is to X"`, the model outputs `"Homemaker"`. Similarly, it might associate certain names or dialects with negative sentiments or specific professions.
- **Mitigation:** Researchers use "de-biasing" techniques, which usually involve identifying a "gender direction" or "race direction" in the vector space and projecting the vectors to neutralize or subtract that specific biased dimension from words that should be neutral (like "doctor" or "nurse").

### 4. Intrinsic vs. Extrinsic Evaluation

These are the two main paradigms for testing how "good" your word embeddings are.

- **Intrinsic Evaluation:** Testing the embeddings directly on isolated, specific sub-tasks to see if they capture language rules properly.
    - _Examples:_ Analogy tasks (`king - man + woman = queen`), or comparing the model's cosine similarities against human-annotated similarity scores (e.g., asking humans to rate how similar "cup" and "mug" are, and seeing if the model's math agrees). It is fast and cheap to compute.
- **Extrinsic Evaluation:** Testing the embeddings by plugging them into a real, downstream NLP task (like Sentiment Analysis or Named Entity Recognition) as the input layer.
    - _How it works:_ If Model A using Word2Vec gets 85% accuracy on an NER task, and Model B using FastText gets 88% on the exact same task, you conclude FastText is the better embedding for that specific use case. It is much slower to compute but reflects real-world utility.

### 5. Dimensionality of Embeddings

This refers to the size of the vector used to represent a word (e.g., 50, 100, 300, or 768 dimensions).

- **The Trade-off:**
    - If the dimensionality is too low (e.g., 10 dimensions), the vector doesn't have enough "space" or capacity to capture all the complex syntactic and semantic nuances of a word.
    - If the dimensionality is too high (e.g., 5,000 dimensions), the model becomes massively expensive to train and store, and it risks overfitting to the training data.
- **Standard Practice:** Classical static embeddings (Word2Vec, GloVe) usually settled on a "sweet spot" of **300 dimensions**. Modern contextual embeddings (like BERT or GPT models) often use much higher dimensions (e.g., 768, 1024, or even 4096+ dimensions) because the networks are significantly larger and trained on drastically more data.
