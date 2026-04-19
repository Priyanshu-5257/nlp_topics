Contextual embeddings mark the major transition point between classical deep learning and the modern Generative AI era. Here is a breakdown of these concepts:

### 1. Context-dependent representations

This is the core concept that revolutionized NLP.

- **The Problem with Static Embeddings:** In Word2Vec or GloVe, the word "bank" receives the exact same mathematical vector regardless of whether the sentence is "I sat by the river bank" or "I deposited money in the bank." The model collapses all meanings of a polysemous word into a single point in space.
- **The Solution:** Contextual embeddings generate a vector for a word _dynamically_, based on the entire sequence of words surrounding it. Therefore, "bank" in the first sentence will have a completely different vector representation than "bank" in the second sentence.

### 2. ELMo (biLSTM-based) (High-Frequency)

ELMo (Embeddings from Language Models) was one of the first massively successful contextual embedding models (released in 2018).

- **How it works:** ELMo is built using a massive, multi-layer **bidirectional LSTM** (biLSTM) neural network. It trains two separate language models simultaneously: one reading the text forward (left-to-right) and one reading it backward (right-to-left).
- **The Representation:** When you feed a sentence into ELMo, it doesn't just look up a static vector. Instead, it processes the sentence through its biLSTM layers. The final contextual embedding for a specific word is calculated by taking a weighted sum of the internal hidden states of _all_ the biLSTM layers for that word. This allows it to capture both shallow syntax (from lower layers) and deep semantics (from higher layers).

### 3. Subword tokenization (High-Frequency)

While earlier models like FastText introduced subword features for _static_ embeddings, modern contextual models require strict subword tokenization to process text efficiently.

- **The Problem:** Traditional word-level tokenization requires massive vocabularies (e.g., 100,000+ words) and still fails on Out-Of-Vocabulary (OOV) words or typos. Character-level tokenization never has OOV issues, but characters carry very little independent meaning, and it makes the input sequences painfully long for a neural network to process.
- **How it works:** Subword tokenization finds the perfect middle ground. It breaks text into frequently occurring chunks. Common words are kept whole (e.g., `"dog"`), but rare or complex words are split into meaningful pieces (e.g., `"unbelievable"` might become `["un", "##believ", "##able"]`).
- **Why it's important:** This is the standard for all modern LLMs. Algorithms like **BPE (Byte Pair Encoding)** and **WordPiece** ensure that a model can handle literally any string of text (no OOV errors) while keeping the vocabulary size manageable (usually around 30,000 to 50,000 subwords).