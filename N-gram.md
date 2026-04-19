The provided document concludes the "Markov Models & Sequence Modeling" chapter with **N-gram Language Models**, identifying nearly all of its subtopics as high-frequency interview questions.

Just as in the previous sections, **please note that the detailed definitions, mathematical expressions, and examples provided below are drawn from outside of your given sources**, as the sources only list the topic names. You may want to independently verify this information.

Here is a detailed breakdown of N-gram Language Models:

### 1. Unigram / Bigram / Trigram

An N-gram is a contiguous sequence of _n_ items (usually words) from a given text. N-gram language models predict the probability of the next word based on the previous $n-1$ words, relying heavily on the Markov property.

- **Unigram (1-gram):** Assumes each word is completely independent of all other words.
    - **Expression:** $P(w_1, w_2, ..., w_m) = \prod_{i=1}^{m} P(w_i)$
- **Bigram (2-gram):** The probability of a word depends only on the _one_ immediately preceding word.
    - **Expression:** $P(w_i | w_{i-1}) = \frac{\text{Count}(w_{i-1}, w_i)}{\text{Count}(w_{i-1})}$
- **Trigram (3-gram):** The probability depends on the _two_ preceding words.
    - **Expression:** $P(w_i | w_{i-2}, w_{i-1}) = \frac{\text{Count}(w_{i-2}, w_{i-1}, w_i)}{\text{Count}(w_{i-2}, w_{i-1})}$
- **NLP Example:** For the sentence "The cat sat":
    - Unigram: $P(\text{The}) \times P(\text{cat}) \times P(\text{sat})$
    - Bigram: $P(\text{The}|\langle s \rangle) \times P(\text{cat}|\text{The}) \times P(\text{sat}|\text{cat})$

### 2. Smoothing: Laplace & Good-Turing

If an n-gram never appeared in the training data, a standard model assigns it a probability of exactly $0$, which zeros out the entire sequence probability. Smoothing solves this by taking a little bit of probability mass from seen events and assigning it to unseen events.

- **Laplace (Add-1) Smoothing:** The simplest approach. You simply add 1 to the count of _every_ possible n-gram in your vocabulary ($V$).
    - **Expression (Bigram):** $P_{Laplace}(w_i | w_{i-1}) = \frac{\text{Count}(w_{i-1}, w_i) + 1}{\text{Count}(w_{i-1}) + |V|}$
- **Good-Turing Smoothing:** A more sophisticated approach based on the "frequency of frequencies." It estimates the probability of unseen n-grams based on the probability of n-grams that only appeared exactly once (singletons). Let $N_c$ be the number of n-grams that appear exactly $c$ times. It adjusts the raw count $c$ to an expected count $c^*$.
    - **Expression:** $c^* = (c + 1) \frac{N_{c+1}}{N_c}$

### 3. Kneser-Ney Smoothing (High-Frequency)

Kneser-Ney is generally considered the most effective standard smoothing technique for n-grams. Rather than just relying on how often a word appears overall, it looks at the **continuation probability**—how many _different_ contexts a word appears in.

- **NLP Example:** The word "Francisco" might appear 500 times in a corpus, but almost always directly after "San". The word "glasses" might only appear 100 times, but it follows many different words ("reading glasses", "water glasses", "broken glasses"). If a model sees a completely novel context, Kneser-Ney assigns a higher probability to "glasses" than "Francisco" because "glasses" is a more versatile continuation word, whereas "Francisco" is rigidly tied to "San".
- **Expression (Absolute Discounting part):** It subtracts a fixed discount $d$ (usually around 0.75) from the counts of seen higher-order n-grams to distribute mass to lower-order n-grams based on this continuation probability.

### 4. Backoff & Interpolation

When a specific higher-order n-gram (like a trigram) is missing from the training data, the model needs a strategy to handle it.

- **Backoff (e.g., Katz Backoff):** The model "backs off" to a lower-order context. If the trigram count is 0, try the bigram. If the bigram count is 0, try the unigram. You apply a penalty weight ($\alpha$) every time you back off so the probabilities still sum to 1.
- **Interpolation (e.g., Jelinek-Mercer):** Instead of only backing off when a count is 0, interpolation _always_ mixes the probabilities of the unigram, bigram, and trigram together using learned weights ($\lambda$).
    - **Expression:** $\hat{P}(w_n | w_{n-2}, w_{n-1}) = \lambda_1 P(w_n) + \lambda_2 P(w_n | w_{n-1}) + \lambda_3 P(w_n | w_{n-2}, w_{n-1})$ (where $\sum \lambda_i = 1$).

### 5. Perplexity as LM Metric

As discussed in the Information Theory section, perplexity is the standard intrinsic evaluation metric for a language model.

- **Expression:** $PP(W) = \sqrt[N]{\prod_{i=1}^{N} \frac{1}{P(w_i | w_{1...i-1})}}$
- **NLP Example:** If you train a trigram model and test it on a holdout set, a lower perplexity means your model assigned a higher probability to the actual text in the test set (i.e., it was less "surprised" by the text).