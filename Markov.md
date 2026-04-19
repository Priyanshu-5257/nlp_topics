The provided document lists these concepts under **Markov Chains** as the first part of the **Markov Models & Sequence Modeling (Foundations)** chapter. Notably, the **Markov property** is highlighted as a high-frequency interview topic.

Just as with the previous sections, **please note that the detailed definitions, mathematical expressions, and examples provided below are drawn from outside of your given sources**, as the sources only list the topic names. You may want to independently verify this mathematical information.

Here is a breakdown of these Markov Chain concepts:

### 1. Markov Property (High-Frequency)

The Markov property is the foundational assumption of Markov models, often described as "memorylessness." It states that the probability of transitioning to the next state depends _only_ on the current state, and not on the sequence of events that preceded it.

- **Expression:** $P(X_{n+1} = x_{n+1} | X_1 = x_1, X_2 = x_2, ..., X_n = x_n) = P(X_{n+1} = x_{n+1} | X_n = x_n)$
- **NLP Example:** In a simple bigram language model, the probability of the next word being "apple" depends only on the immediate preceding word (e.g., "green"), ignoring all other words that came earlier in the sentence.

### 2. Transition Matrix

A transition matrix defines the probabilities of moving from any given state to any other state in a single step within a Markov Chain.

- **Expression:** A square matrix $P$ where the entry $P_{ij}$ represents the probability of moving from state $i$ to state $j$: $P_{ij} = P(X_{n+1} = j | X_n = i)$. The sum of probabilities in every row must equal exactly 1 ($\sum_j P_{ij} = 1$).
- **NLP Example:** If you have a vocabulary of 10,000 words, you could create a $10,000 \times 10,000$ transition matrix where each cell represents the probability of word $j$ following word $i$ based on a large text corpus.

### 3. Stationary Distribution

A stationary distribution is a probability distribution over the states that remains unchanged as time progresses. If a Markov chain reaches this distribution, the probabilities of being in each state will stay constant for all future steps.

- **Expression:** A row vector $\pi$ such that $\pi P = \pi$, where $P$ is the transition matrix.
- **Example:** Google's original PageRank algorithm uses a Markov chain where the "states" are web pages. The stationary distribution represents the long-term probability of a random web surfer landing on any specific page, which translates to that page's "rank" or importance.

### 4. Ergodicity

An ergodic Markov chain is one that is both _irreducible_ (you can eventually get from any state to any other state) and _aperiodic_ (it doesn't get trapped in deterministic, repeating cycles). A key property of ergodic chains is that they will always converge to a unique stationary distribution, regardless of the starting state.

- **NLP Example:** If a text generation model strictly generates "A B A B A B..." forever, it is periodic (not ergodic). If a model can transition between all characters in the alphabet without getting permanently stuck in a sub-loop, it is ergodic, meaning over an infinite amount of generated text, the frequency of each character will stabilize to a fixed distribution.

### 5. n-th Order Markov Models

Standard Markov chains are "first-order," meaning the next state depends only on the 1 previous state. An $n$-th order Markov model relaxes this slightly by allowing the next state to depend on the previous $n$ states.

- **Expression:** $P(X_t | X_{t-1}, X_{t-2}, ..., X_1) = P(X_t | X_{t-1}, ..., X_{t-n})$
- **NLP Example:** While a bigram model is a 1st-order Markov model (depends on 1 previous word), a **trigram** language model is a 2nd-order Markov model because predicting the 3rd word relies on the previous 2 words. This provides more context but requires exponentially more data to calculate the transition probabilities.