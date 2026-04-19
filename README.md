# NLP Topic Map

A structured map of Natural Language Processing topics from foundations to modern LLMs.

**Legend:**
*   **Foundations**: Probability, Stats, and Markov Models
*   **Classical NLP**: Preprocessing, Syntax, and Traditional ML
*   **Neural Era**: RNNs, CNNs, and Word Embeddings
*   **Modern / GenAI**: Transformers, LLMs, and Fine-tuning
*   **Evaluation & MLOps**: Metrics and Productionization

> **Note:** **Bold items** represent high-frequency interview questions.

---

## 1. Probability & Information Theory (Foundations)

*   **Core Probability** [Probability](./Probability.md)
    *   **Bayes' theorem**
    *   Conditional probability
    *   Chain rule of probability
    *   Joint & marginal distributions
    *   **MLE vs MAP**
    *   Prior, likelihood, and posterior
*   **Distributions** [Distributions](./Distributions.md)
    *   Gaussian / Normal
    *   **Categorical & Multinomial**
    *   Dirichlet distribution
    *   Bernoulli & Binomial
    *   Poisson
    *   Beta distribution
*   **Information Theory** [colah.github](https://colah.github.io/posts/2015-09-Visual-Information/)
    *   **Entropy (Shannon)**  [medium](https://medium.com/@_prinsh_u/understanding-shannon-entropy-and-kl-divergence-through-information-theory-e201b8279e62)
    *   **Cross-entropy**
    *   **KL divergence**  [medium](https://medium.com/@_prinsh_u/understanding-shannon-entropy-and-kl-divergence-through-information-theory-e201b8279e62)
    *   Mutual information
    *   **Perplexity** [Perplexity](./Perplexity.md)
    *   Jensen-Shannon divergence [medium](https://medium.com/@_prinsh_u/getting-to-know-jensen-shannon-divergence-jsd-5c96720a4434)
*   **Statistics Fundamentals**
    *   Expectation & variance [Probability](./Probability.md)
    *   Law of large numbers [pdf link](https://math.mit.edu/~dav/05.dir/class6-prep.pdf)
    *   Central limit theorem  [pdf link](https://math.mit.edu/~dav/05.dir/class6-prep.pdf)
    *   Hypothesis testing [link](https://github.com/The-Pocket/PocketFlow-Tutorial-Video-Generator/blob/main/docs/stats/hypothesis.md)
    *   p-values & confidence intervals [link](https://github.com/The-Pocket/PocketFlow-Tutorial-Video-Generator/blob/main/docs/stats/hypothesis.md)

---

## 2. Markov Models & Sequence Modeling (Foundations)

*   **Markov Chains** [Markov](./Markov.md)
    *   **Markov property**
    *   Transition matrix
    *   Stationary distribution
    *   Ergodicity
    *   n-th order Markov models
*   **Hidden Markov Models (HMM)** [Hidden Markov](./Hidden%20Markov.md)
    *   **Emission & transition probabilities**
    *   **Forward algorithm**
    *   Backward algorithm
    *   **Viterbi algorithm**
    *   **Baum-Welch (EM for HMM)**
    *   POS tagging with HMM
*   **N-gram Language Models** [N-gram](./N-gram.md)
    *   **Unigram / bigram / trigram**
    *   **Smoothing: Laplace, Good-Turing**
    *   **Kneser-Ney smoothing**
    *   Perplexity as LM metric
    *   Backoff & interpolation

---

## 3. Classical NLP Methods (Classical)

*   **Text Preprocessing** [link](https://medium.com/@devangchavan0204/complete-guide-to-text-preprocessing-in-nlp-b4092c104d3e)
    *   **Tokenization**
    *   **Stemming vs lemmatization**
    *   Stop-word removal
    *   Lowercasing & normalization
    *   Regular expressions
    *   Sentence segmentation
*   **Feature Representations**
    *   **Bag of Words (BoW)** [medium](https://medium.com/analytics-vidhya/fundamentals-of-bag-of-words-and-tf-idf-9846d301ff22)
    *   **TF-IDF**
    *   N-gram features
    *   One-hot encoding [medium](https://medium.com/@sateeshfrnd/breaking-down-one-hot-encoding-for-text-data-in-nlp-fdd8a8df60f4)
    *   Sparse vs dense vectors
*   **Syntax & Parsing** [Syntax and Parsing](./Syntax%20and%20Parsing.md)
    *   **POS tagging**
    *   Constituency parsing
    *   **Dependency parsing**
    *   CFG & CYK algorithm
    *   Chunking / shallow parsing
*   **Lexical Semantics** [Lexical Semantics](./Lexical%20Sementics.md)
    *   WordNet & synsets
    *   WSD (Word Sense Disambiguation)
    *   Coreference resolution
    *   Semantic role labeling
*   **Classical ML for NLP** [Classical ML for NLP](./Classical%20ML%20for%20NLP.md)
    *   Logistic regression
    *   **Naive Bayes classifier**
    *   **SVM for text**
    *   Decision trees / random forests
    *   **CRF (Conditional Random Fields)**
    *   **MEMM (Max-Entropy Markov Models)**

---

## 4. Word Embeddings & Representations (Neural Era)

*   **Static Embeddings** [Static Embedding](./Static%20Embedding.md)
    *   **Word2Vec (CBOW & Skip-gram)**
    *   **GloVe**
    *   **FastText (subword)**
    *   **Negative sampling**
    *   Noise contrastive estimation
    *   Analogy tasks (king-man+woman)
*   **Embedding Properties** [Embedding Properties](./Embedding%20Properties.md)
    *   **Cosine similarity**
    *   Nearest neighbor search
    *   **Bias in embeddings**
    *   Intrinsic vs extrinsic evaluation
    *   Dimensionality of embeddings
*   **Contextual Embeddings** [Contextual Embeddings](./Contextual%20Embeddings.md)
    *   **ELMo (biLSTM-based)**
    *   Context-dependent representations
    *   **Subword tokenization**

---

## 5. Neural Network Architectures (Neural Era)

*   **RNNs & Variants**
    *   **Vanilla RNN & vanishing gradient** [blog](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
    *   **LSTM (cell, input, forget, output gates)**
    *   **GRU** [youtube](https://www.youtube.com/watch?v=QQfZAoNGQmE)
    *   **Bidirectional RNN/LSTM** [youtube](https://www.youtube.com/watch?v=k2NSm3MNdYg)
    *   **Sequence-to-sequence (Seq2Seq)** [medium](https://medium.com/analytics-vidhya/a-simple-introduction-to-sequence-to-sequence-models-b34ebdf113a5)
    *   **Teacher forcing**
*   **CNNs for NLP** [medium](https://medium.com/@conniezhou678/mastering-natural-language-processing-part-23-understanding-convolutional-neural-networks-cnns-98b4e434bba6)
    *   1D convolutions over text
    *   **TextCNN (Kim 2014)**
    *   N-gram capture with filters
    *   Max-over-time pooling
*   **Attention Mechanisms** [medium](https://medium.com/@akanyaani/evolution-of-attention-mechanisms-in-nlp-from-additive-to-self-attention-01e265925899)
    *   **Bahdanau (additive) attention**
    *   **Luong (multiplicative) attention**
    *   **Self-attention**
    *   **Scaled dot-product attention**
    *   **Multi-head attention**
    *   **Key, Query, Value (QKV)**
*   **Training Fundamentals**
    *   **Backprop through time (BPTT)**
    *   Gradient clipping [medium](https://medium.com/data-science/what-is-gradient-clipping-b8e815cdfb48)
    *   Dropout & regularization
    *   Label smoothing
    *   **Beam search vs greedy** [YT](https://www.youtube.com/watch?v=tOhWpF5-_z4)

---

## 6. Transformers & Pre-trained Models (Modern / GenAI)

*   **Transformer Architecture**
    *   **Positional encoding (sinusoidal)**
    *   **Layer normalization**
    *   Feed-forward sublayer
    *   **Residual connections**
    *   **Encoder vs decoder vs enc-dec**
    *   Cross-attention
*   **Tokenization (Deep Dive)**
    *   **BPE (Byte Pair Encoding)**
    *   **WordPiece tokenization**
    *   **SentencePiece / Unigram LM**
    *   Byte-level BPE (GPT-2)
    *   Vocabulary size tradeoffs
    *   **OOV handling**
*   **BERT-family (Encoder)**
    *   **MLM (Masked Language Modeling)**
    *   **NSP (Next Sentence Prediction)**
    *   RoBERTa improvements
    *   ALBERT (factorized embedding)
    *   DistilBERT (knowledge distillation)
    *   SpanBERT
*   **GPT-family (Decoder)**
    *   **Causal (autoregressive) LM**
    *   GPT-1/2/3/4 scaling
    *   **In-context learning (ICL)**
    *   **Few-shot / zero-shot prompting**
    *   Next-token prediction objective
*   **Encoder-Decoder Models**
    *   **T5 (text-to-text framework)**
    *   **BART (denoising pretraining)**
    *   mT5 / mBART (multilingual)
    *   Prefix LM vs causal LM
*   **Efficient Transformers**
    *   **Sparse attention (Longformer, BigBird)**
    *   **Linear attention**
    *   **Flash Attention**
    *   Sliding window attention
    *   Performer (FAVOR+)

---

## 7. Core NLP Tasks (Classical + Modern)

*   **Classification**
    *   **Sentiment analysis**
    *   Topic classification
    *   **Intent detection**
    *   Spam / toxic detection
    *   Multi-label classification
*   **Sequence Labeling**
    *   **NER (Named Entity Recognition)**
    *   POS tagging
    *   Chunking
    *   **BIO / BIOES tagging scheme**
*   **Generation**
    *   **Machine translation**
    *   **Text summarization (extractive vs abstractive)**
    *   **Question answering (extractive & generative)**
    *   Dialogue & chatbots
    *   Story generation
*   **Parsing & Structure**
    *   **Dependency parsing**
    *   Coreference resolution
    *   Semantic role labeling
    *   **Relation extraction**
    *   Event extraction
*   **Information Retrieval**
    *   TF-IDF retrieval
    *   **BM25**
    *   **Dense retrieval (bi-encoder)**
    *   **Cross-encoder reranking**
    *   **RAG (Retrieval-Augmented Gen)**

---

## 8. Fine-tuning, Alignment & PEFT (Modern / GenAI)

*   **Transfer Learning Paradigms**
    *   **Feature extraction vs fine-tuning**
    *   Catastrophic forgetting
    *   Domain adaptation
    *   Multi-task learning
*   **Parameter-Efficient Fine-Tuning (PEFT)**
    *   **LoRA (Low-Rank Adaptation)**
    *   **QLoRA (quantized LoRA)**
    *   Adapter layers
    *   **Prefix tuning**
    *   Prompt tuning
    *   IA3
*   **Instruction Tuning & Alignment**
    *   **Instruction tuning (FLAN, Alpaca)**
    *   **RLHF (Reward Model + PPO)**
    *   **DPO (Direct Preference Optimization)**
    *   Constitutional AI
    *   RLAIF
*   **Prompting Strategies**
    *   **Zero-shot & few-shot**
    *   **Chain-of-thought (CoT)**
    *   **Self-consistency**
    *   **ReAct (reason + act)**
    *   Tree-of-thought
    *   Prompt injection & robustness

---

## 9. Modern GenAI & LLM Internals (Modern / GenAI)

*   **Scaling & Emergent Behavior**
    *   **Scaling laws (Chinchilla)**
    *   Emergent abilities
    *   Grokking
    *   **In-context learning theory**
*   **Decoding Strategies**
    *   Greedy decoding
    *   **Beam search**
    *   **Top-k sampling**
    *   **Top-p (nucleus) sampling**
    *   **Temperature scaling**
    *   Repetition penalty
*   **Positional & Context Extensions**
    *   **RoPE (Rotary Position Embedding)**
    *   **ALiBi**
    *   NTK-aware interpolation
    *   YaRN
    *   Long-context fine-tuning
*   **Architecture Innovations**
    *   **Mixture of Experts (MoE)**
    *   **GQA (Grouped Query Attention)**
    *   MLA (Multi-head Latent Attention)
    *   **KV cache**
    *   **Speculative decoding**
    *   **State Space Models (Mamba)**
*   **Quantization & Compression**
    *   **INT8 / INT4 quantization**
    *   GPTQ
    *   AWQ
    *   **Knowledge distillation**
    *   Pruning
    *   Structured vs unstructured pruning
*   **Agents & Tool Use**
    *   **Tool-calling / function calling**
    *   **RAG pipelines**
    *   Agentic loops
    *   Memory (episodic, semantic)
    *   Multi-agent coordination

---

## 10. Evaluation & Metrics (Eval & MLOps)

*   **Classification Metrics**
    *   **Precision, recall, F1**
    *   **Macro vs micro vs weighted avg**
    *   ROC-AUC
    *   Matthews correlation coefficient
    *   Confusion matrix
*   **Generation Metrics**
    *   **BLEU**
    *   **ROUGE (R-1, R-2, R-L)**
    *   METEOR
    *   **BERTScore**
    *   **Perplexity** [Perplexity](./Perplexity.md)
    *   MoverScore
*   **LLM-specific Eval**
    *   **Hallucination detection**
    *   Faithfulness vs factuality
    *   **LLM-as-judge**
    *   MT-bench / Chatbot Arena
    *   **MMLU, HumanEval**
*   **MLOps for NLP**
    *   Experiment tracking (MLflow, W&B)
    *   Model versioning
    *   Data versioning (DVC)
    *   **Serving (vLLM, TGI)**
    *   Latency vs throughput tradeoffs
    *   A/B testing NLP models

---

## Learning Path

```
Foundations → Classical NLP → Neural Era → Modern/GenAI
```

Each section links to detailed notes in this repository.

## Youtube Channels I follow - 

[ZacharyLLM](https://www.youtube.com/@ZacharyLLM)
[1littlecoder](https://www.youtube.com/@1littlecoder)
[AndrejKarpathy](https://www.youtube.com/@AndrejKarpathy)
[Deepia](https://www.youtube.com/@Deepia-ls2fo)
[EfficientNLP](https://www.youtube.com/@EfficientNLP)
[jbhuang0604](https://www.youtube.com/@jbhuang0604)
[juliaturc](https://www.youtube.com/@juliaturc1)
[PapersAreWonderful](https://www.youtube.com/@PapersAreWonderful)
[engineerprompt](http://youtube.com/@engineerprompt)
[very-normal](https://www.youtube.com/@very-normal)
[WelchLabs](http://youtube.com/@WelchLabs)
[campusx](https://www.youtube.com/@campusx-official)
