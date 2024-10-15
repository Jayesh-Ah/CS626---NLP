# CS 626 (Natural Language Processing)
## 🤖 HMM POS Tagging
Project Overview
This project implements a Part-of-Speech (POS) tagging system using Hidden Markov Model (HMM) and the Viterbi Algorithm. The goal is to tag sequences of words from the Brown corpus with their corresponding POS tags using a probabilistic model. The POS tags are based on the Universal Tag Set, and the system undergoes 5-fold cross-validation to ensure robustness.

### Key Components

- Data Preprocessing: The input text is tokenized, lowercase transformations are applied, and sentence boundaries are defined with start and end tokens.
- HMM Model: The model is trained using the Brown corpus, computing transition and emission probabilities to determine the most likely sequence of tags for a given sentence.
- Viterbi Algorithm: Utilized for decoding the POS tag sequence, ensuring optimal backtracking to assign the most probable tag sequence for each word.
- Performance Metrics:
-- Precision: 0.9484
-- Recall: 0.9348
-- F1-Score: 0.9334
### Challenges

- Contextual Confusion: The model struggled with ambiguous words like "fish" and "running," confusing nouns and verbs.
- Error Analysis: Confusion matrices revealed that the model was not fully capturing contextual nuances and had issues with polysemous words.
### Learning Outcomes

Hands-on experience with probabilistic modeling and sequence labeling.
Gained understanding of the limitations of HMMs, particularly in handling complex contexts.
## 🤖 CRF POS Tagging
Project Overview
This project extends POS tagging capabilities using a Conditional Random Field (CRF) model. Unlike HMM, CRF models consider the entire sentence as a whole, leveraging contextual information and additional features to improve tagging accuracy. The system is also tested on the Brown corpus using the Universal Tag Set, with 5-fold cross-validation applied.

### Key Components

- Feature Extraction:
-- Suffix and Prefix Analysis: Extracts features from the last two and three characters of each word to identify common suffixes.
-- Position-Based Features: Incorporates features for the first and last words of a sentence, surrounding words, and word structure (e.g., hyphens, numbers).
-- Capitalization Features: Identifies capitalization patterns and internal capital letters in words.
- CRF Model: Captures both word-level and contextual features to predict the most accurate POS tags.
- Performance Metrics:
-- Precision: 0.991
-- Recall: 0.984
-- F1-Score: 0.987
### Challenges

- Memory Overload: High RAM usage during feature extraction, especially for unknown words and embeddings, led to performance issues.
- Handling Ambiguity: The model successfully handled ambiguous words by leveraging context but faced difficulty with memory limitations for large datasets.
## Comparison with HMM
CRF outperformed HMM in handling polysemous words and considering contextual information, such as distinguishing between "to" as a particle and a preposition, where HMM struggled.

### Learning Outcomes

- Learned how to implement feature-rich sequence models like CRF for POS tagging.
- Gained insights into contextual tagging and the advantages of CRFs over HMMs for certain NLP tasks.
