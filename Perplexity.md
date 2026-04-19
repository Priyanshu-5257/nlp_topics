### 5. Perplexity

Perplexity is a standard evaluation metric for language models. It is the exponentiated cross-entropy. Intuitively, it represents the average branching factor of the model—how "confused" the model is when predicting the next word. **Lower perplexity is better.**

- **Expression:** $\text{Perplexity}(P) = 2^{H(P)}$ (if using base-2 logs), or more practically for a sequence of $N$ words: $PP = \exp(-\frac{1}{N} \sum_{i=1}^{N} \log P(x_i | x_{<i}))$
- **Example:** If a language model has a perplexity of 10 on a test dataset, it means that at each step, the model is as uncertain as if it were choosing from a 10-sided die of equally likely next words.
[[Perplexity]]