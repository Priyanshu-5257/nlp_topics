
### 1. WordNet & Synsets

WordNet is a massive, publicly available lexical database of English (and other languages) that acts like a highly structured dictionary/thesaurus.

- **Synsets:** Instead of just listing words alphabetically, WordNet groups words into sets of cognitive synonyms called "synsets" (e.g., _car, auto, automobile, machine, motorcar_ form one synset).
- **Relations:** WordNet maps the relationships between these synsets, such as hypernyms (is-a-kind-of, e.g., a dog is a canine) and meronyms (is-a-part-of, e.g., a wheel is part of a car).
- **Why it's used:** In classical NLP, WordNet is used to calculate word similarity and help algorithms understand that two completely different strings (like "dog" and "hound") actually represent the same concept.

### 2. WSD (Word Sense Disambiguation)

Many words in English are polysemous—they have multiple meanings depending on context. WSD is the algorithmic task of figuring out exactly _which_ meaning (or "sense") of a word is being used in a specific sentence.

- **How it works:** Classical approaches often use the Lesk Algorithm, which compares the dictionary definition (from something like WordNet) of a target word with the definitions of the words surrounding it in the sentence to find the highest lexical overlap.
- **NLP Example:** In the sentence `"I need to deposit money in the bank"`, a WSD algorithm determines that "bank" refers to a financial institution, not the side of a river, because of the surrounding context words like "deposit" and "money".

### 3. Coreference Resolution

This is the task of finding all expressions (mentions) in a text that refer to the same underlying real-world entity.

- **How it works:** It involves identifying pronouns and noun phrases and linking them together into "coreference chains."
- **NLP Example:** In the text `"Jane dropped her apple. She was sad because it got dirty"`, coreference resolution figures out that `["Jane", "her", "She"]` all point to the same person, and `["apple", "it"]` point to the same object. This is notoriously difficult when grammar is ambiguous.

### 4. Semantic Role Labeling (SRL)

Also known as shallow semantic parsing, SRL answers the question: _"Who did what to whom, where, when, and how?"_ It assigns semantic roles (like Agent, Patient/Theme, Instrument, Location) to the constituents of a sentence, usually centered around a predicate (the main verb).

- **NLP Example:** In the sentence `"The boy smashed the window with a rock"`:
    - `"smashed"` is the Predicate.
    - `"The boy"` is the Agent (the doer of the action).
    - `"the window"` is the Theme/Patient (the thing affected by the action).
    - `"with a rock"` is the Instrument (the tool used).
- **Why it's useful:** It allows models to understand that `"The boy smashed the window"` and `"The window was smashed by the boy"` describe the exact same event, even though their syntactic structures (dependency parsing trees) look completely different.

### 5. Lexical Overlap

Lexical overlap is a very simple, classical heuristic used to determine the similarity between two sentences or documents by calculating how many words they share.

- **How it works:** You extract the vocabulary of both texts (often after removing stop-words and applying stemming) and calculate a metric like Jaccard Similarity (the size of the intersection divided by the size of the union of the two word sets).
- **Limitation:** Because it only looks at exact surface-level words, it fails to capture semantic similarity. For instance, `"The canine chased the feline"` and `"The dog ran after the cat"` have zero lexical overlap, even though they mean the same thing.