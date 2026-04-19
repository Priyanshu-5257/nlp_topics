

An HMM is a statistical Markov model in which the system being modeled is assumed to be a Markov process with unobservable (i.e., _hidden_) states. While we cannot see the states themselves, we can see _observations_ that depend on those states.

Here is a breakdown of the key HMM components and algorithms:

### 1. Emission & Transition Probabilities

These two matrices define the core mechanics of an HMM.

- **Transition Probabilities ($A$):** The probability of moving from one hidden state to another. Just like a standard Markov Chain, $A_{ij}$ is the probability of transitioning from state $i$ to state $j$.
- **Emission Probabilities ($B$):** The probability of a hidden state "emitting" or generating a specific visible observation. $B_{ik}$ is the probability of generating observation $k$ while in hidden state $i$.

### 2. POS Tagging with HMM (An NLP Example)

To make the following algorithms easier to understand, Part-of-Speech (POS) tagging is the classic NLP application of HMMs.

- **Hidden States:** The POS tags (e.g., Noun, Verb, Adjective). They are "hidden" because when we read a sentence, we only see the words, not the tags.
- **Observations:** The actual words in the text (e.g., "bank", "run", "fast").
- **Transition ($A$):** The probability that a Noun is followed by a Verb.
- **Emission ($B$):** The probability that the tag "Verb" emits the specific word "run".

### 3. Forward Algorithm

This algorithm answers the question: _Given an HMM, what is the total probability of seeing a specific sequence of observations?_

- **How it works:** Instead of calculating the probability of every possible path of hidden states (which is computationally impossible for long sequences), the Forward algorithm uses dynamic programming. It calculates the probability of being in each state at time $t$ having seen the observations up to time $t$, and passes those probabilities _forward_ to time $t+1$.
- **NLP Example:** What is the total probability that a language model generates the exact sequence of words "The cat sat"?

### 4. Backward Algorithm

This is the mirror image of the Forward algorithm. It computes the probability of seeing the _remaining_ sequence of observations from time $t+1$ to the end, given that we are in a specific state at time $t$.

- **Why it's used:** On its own, it's rarely used for inference. However, combining the Forward and Backward probabilities allows us to pinpoint the probability of being in a specific hidden state at a specific time, which is essential for the Baum-Welch training algorithm.

### 5. Viterbi Algorithm (High-Frequency)

The Viterbi algorithm answers the decoding question: _Given an observation sequence, what is the single most likely sequence of hidden states that produced it?_

- **How it works:** Like the Forward algorithm, it uses dynamic programming. However, instead of _summing_ the probabilities of all incoming paths to a state, Viterbi takes the _maximum_ probability. It keeps track of the "best path" to reach every state at every time step. Once it reaches the end of the sequence, it backtracks to reveal the optimal path.
- **NLP Example:** Given the sentence "I bank at the bank", Viterbi determines that the most likely sequence of hidden states (POS tags) is `[Pronoun, Verb, Preposition, Determiner, Noun]`.

### 6. Baum-Welch (EM for HMM)

Baum-Welch is an unsupervised learning algorithm used to _train_ an HMM when you only have observation sequences and no hidden state labels. It is a specific application of the Expectation-Maximization (EM) algorithm.

- **How it works:**
    1. Start with random Transition and Emission probabilities.
    2. **E-step (Expectation):** Use the Forward and Backward algorithms to estimate the expected frequencies of state transitions and emissions given the current data.
    3. **M-step (Maximization):** Update the Transition and Emission matrices to maximize the likelihood of these expected frequencies.
    4. Repeat until the probabilities converge.
- **NLP Example:** If you give Baum-Welch a massive corpus of raw English text without any POS tags, it will eventually cluster the words into hidden states that loosely mimic grammatical rules (e.g., it will learn that certain words group together and frequently follow other specific groups of words), updating its internal transition and emission matrices to reflect these patterns.