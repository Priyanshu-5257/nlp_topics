
### 1. Naive Bayes Classifier (High-Frequency)

Naive Bayes is a probabilistic, "generative" classifier based on applying Bayes' theorem. It is famous for being simple, incredibly fast, and very effective as a baseline for text classification (like spam filtering).

- **The "Naive" Assumption:** It assumes that every feature (word) in a document is conditionally independent of every other feature, given the class label. Even though this is linguistically false (e.g., the word "New" heavily influences the probability of the word "York"), the classifier still works surprisingly well in practice.
- **Expression:** To classify a document $D$ (made of words $w_1, w_2, ..., w_n$) into a class $C$: $P(C|D) \propto P(C) \prod_{i=1}^{n} P(w_i|C)$
- **How it works:** It calculates the prior probability of each class $P(C)$, and multiplies it by the probability of seeing each individual word given that class $P(w_i|C)$. The class with the highest resulting score wins. (Smoothing, like Laplace smoothing, is strictly required here so that an unseen word doesn't zero out the entire probability).

### 2. Logistic Regression

Despite its name, Logistic Regression is a "discriminative" classification algorithm, not a regression algorithm.

- **How it works:** Instead of modeling how the data was generated (like Naive Bayes), it directly models the boundary between classes. It computes a weighted sum of the input features (e.g., the TF-IDF values of the words) and passes that sum through a logistic (sigmoid) function to output a probability between 0 and 1.
- **Expression:** $P(y=1|x) = \frac{1}{1 + e^{-(w \cdot x + b)}}$ (where $w$ are the learned weights and $x$ is the feature vector).
- **NLP Application:** It is widely used for binary text classification, such as sentiment analysis (Positive vs. Negative). It performs well when you have a lot of data and features are correlated (which Naive Bayes handles poorly).

### 3. SVM for Text (High-Frequency)

Support Vector Machines (SVM) are powerful, discriminative classifiers that attempt to find the optimal "hyperplane" (a dividing line or plane) that separates different classes with the maximum possible margin.

- **Why it's great for text:** Classical NLP features (like Bag-of-Words or TF-IDF) create heavily sparse, high-dimensional vectors (e.g., a 50,000-dimensional space where most values are 0). SVMs are mathematically highly robust to high-dimensional spaces and are less prone to overfitting than other models in this scenario.
- **Linear SVM:** For text classification, a linear kernel is almost always used because text data is usually linearly separable in such high dimensions.

### 4. Decision Trees & Random Forests

These are non-linear models that make classifications by splitting the data into subsets based on feature values, forming a tree-like structure of "if-then-else" rules.

- **Random Forests:** An ensemble method that trains dozens or hundreds of Decision Trees on random subsets of the data and features, and then averages their predictions. This prevents the severe overfitting that single decision trees suffer from.
- **NLP Application:** While excellent for tabular data, they are generally _less_ popular for sparse BoW/TF-IDF text data compared to SVMs or Logistic Regression, because splitting on thousands of highly sparse features is computationally expensive and inefficient. However, they work well with dense word embeddings.

### 5. MEMM (Max-Entropy Markov Models) (High-Frequency)

MEMMs are a discriminative alternative to the generative Hidden Markov Models (HMMs) used for sequence labeling tasks like POS tagging.

- **The Problem with HMMs:** HMMs assume that the current observation only depends on the current hidden state. In reality, a word's POS tag might depend heavily on capitalization, suffixes, or surrounding words.
- **How MEMM works:** It replaces the HMM's transition and emission probabilities with a single, unified Logistic Regression (Maximum Entropy) classifier for each state transition. This allows the model to look at any arbitrary, overlapping features of the entire input sequence to predict the next state.
- **The "Label Bias" Flaw:** MEMMs suffer from the "label bias problem." Because the probabilities leaving any given state must sum to 1, states with very few outgoing transitions have an unfair advantage over states with many outgoing transitions, heavily skewing the model's routing.

### 6. CRF (Conditional Random Fields) (High-Frequency)

CRFs were specifically designed to solve the label bias problem of MEMMs. They are widely considered the absolute pinnacle of classical machine learning for sequence labeling tasks (especially Named Entity Recognition - NER).

- **How it works:** Instead of predicting the next state one step at a time and normalizing the probabilities locally at each state (like an MEMM), a CRF evaluates the entire sequence of states at once. It calculates a global score for the entire predicted sequence and normalizes it over all possible sequences.
- **Why it's powerful:** Because it optimizes globally, it can gracefully handle complex dependencies between labels (e.g., it can easily learn that an "Inside-Organization" tag strongly prefers to follow a "Begin-Organization" tag) without falling into the label bias trap.
