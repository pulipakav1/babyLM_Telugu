# babyLM_Telugu
This project contains work on training a BabyLM (small transformer-based language model) for Telugu using **Curriculum Learning** and **Child-Directed Speech** strategies. Telugu is a low-resource Dravidian language, and our goal is to explore methods that improve model efficiency and accuracy with limited data.

# Data
The data is sourced from news texts, telugu learning textbooks for kids and GPT generated Child-directed sentences. 
- **Corpus Size**: ~447,000 Telugu sentences
- **Scoring**:
  - **Sentence Length**: Shorter sentences considered easier
  - **Word Frequency**: Sentences with more common words prioritized
- **Curriculum Ordering**: Sentences sorted from easy to hard using a scoring function
- **Tokenization**: Basic word-level tokenizer used for all training setups


# Overview
- **Curriculum Learning:** Ordered data from easy to difficult based on sentence length and word rarity.
- **Child-Directed Data:** Simpler, early-learning Telugu sentences.
- **Random Baseline:** For comparison with traditional training approaches.
- **Transformer Architecture:** Lightweight model focusing on training stability.
- **Evaluation Metrics:**
  - Validation Perplexity
  - Minimal Pair Grammar Testing (correct vs. incorrect Telugu sentences)

# Model
- **Architecture**: Small transformer (BabyLM-style)
- **Tokenizer**: Word-level (no BPE or subword)
- **Training Variants**:
  1. **Curriculum Model**: Sorted, progressive training
  2. **Child-Directed Model**: Simplified speech-like sentences
  3. **Random Model**: Shuffled sentences as baseline
- **Evaluation Metrics**:
  - **Validation Perplexity** (lower is better)
  - **Minimal Pair Accuracy** (grammatical correctness preference)

# Findings 
## 📈 Results

| Model           | Validation Perplexity | Minimal Pair Accuracy  |
|---------------- |-----------------------|------------------------|
| **Curriculum**  | **13.47**             | **86%**                |
| Child-Directed  | 18.07                 | 72%                    |
| Random          | 62.64                 | 59%                    |

✅ **Curriculum-based training** achieved the **lowest perplexity (13.47)** and the highest grammatical accuracy (86%), proving most effective.  
✅ **Child-directed data** also led to significant improvements over the random approach.  
❌ **Random training** produced the **highest perplexity (62.64)**, confirming inefficient learning.


