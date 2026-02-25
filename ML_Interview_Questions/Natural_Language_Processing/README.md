# Natural Language Processing (NLP) Interview Questions

This folder contains interview questions focused on Natural Language Processing concepts, techniques, and models.

## Topics Covered

1. **Text Preprocessing**
2. **Word Embeddings**
3. **Sequence Models**
4. **Language Models**
5. **NLP Applications**

---

## Questions

### 1. What is tokenization and why is it important?
**Answer:** Tokenization is the process of breaking text into smaller units (tokens) such as words, subwords, or characters. It's the first step in NLP pipelines. Types include:
- **Word tokenization**: Split by whitespace/punctuation
- **Subword tokenization**: BPE, WordPiece, SentencePiece (used in BERT, GPT)
- **Character tokenization**: Individual characters

### 2. Explain the difference between stemming and lemmatization.
**Answer:** 
- **Stemming**: Rule-based reduction to word stems (e.g., "running" → "runn"). Faster but may produce non-words.
- **Lemmatization**: Reduces words to their dictionary form (lemma) using vocabulary and morphological analysis (e.g., "running" → "run"). More accurate but slower.

### 3. What is TF-IDF and how does it work?
**Answer:** TF-IDF (Term Frequency-Inverse Document Frequency) is a statistical measure of word importance:
- **TF**: How often a term appears in a document
- **IDF**: log(N / df), where N is the total number of documents and df is the number of documents containing the term
- **TF-IDF = TF × IDF**: High for words frequent in a document but rare across corpus
Used for document representation, keyword extraction, and information retrieval.

### 4. Explain Word2Vec and its training approaches.
**Answer:** Word2Vec creates dense vector representations of words:
- **CBOW (Continuous Bag of Words)**: Predicts target word from context words
- **Skip-gram**: Predicts context words from target word
Key properties: Semantic similarity (king - man + woman ≈ queen), captures word relationships, typically 100-300 dimensions.

### 5. What is the attention mechanism in NLP?
**Answer:** Attention allows models to focus on relevant parts of input when generating output:
- Computes similarity scores between query and key vectors
- Applies softmax to get attention weights
- Returns weighted sum of value vectors
Types: Additive (Bahdanau), multiplicative (Luong), self-attention (Transformer). Improves handling of long sequences and interpretability.

### 6. Explain BERT and how it differs from traditional language models.
**Answer:** BERT (Bidirectional Encoder Representations from Transformers):
- **Bidirectional**: Considers both left and right context simultaneously (vs. unidirectional GPT)
- **Pre-training tasks**: Masked Language Modeling (MLM) and Next Sentence Prediction (NSP)
- **Fine-tuning**: Pre-trained model adapted for specific tasks
Key innovation: Deep bidirectional understanding of language context.

### 7. What is named entity recognition (NER)?
**Answer:** NER identifies and classifies named entities in text into categories like:
- Person names
- Organizations
- Locations
- Dates/times
- Monetary values
Approaches: Rule-based, CRF, BiLSTM-CRF, Transformer-based (BERT-NER). Used in information extraction, question answering, and search.

### 8. How do you handle out-of-vocabulary (OOV) words?
**Answer:** Strategies include:
- **Subword tokenization**: BPE, WordPiece break unknown words into known subwords
- **Character-level models**: Handle any character sequence
- **FastText**: Uses character n-grams, can generate embeddings for OOV words
- **UNK token**: Replace with unknown token (loses information)

### 9. What is the difference between seq2seq and transformer models?
**Answer:** 
- **Seq2Seq**: Encoder-decoder RNN architecture, processes sequentially, limited by fixed-length context vector, struggles with long sequences
- **Transformers**: Use self-attention, process all positions in parallel, better long-range dependencies, more efficient training
Transformers have largely replaced seq2seq for most NLP tasks.

### 10. Explain the concept of language model perplexity.
**Answer:** Perplexity measures how well a language model predicts a sequence:
- Perplexity = 2^(cross-entropy loss)
- Lower perplexity = better model
- Represents average number of choices the model is uncertain between
For a vocabulary of size V with uniform distribution, perplexity = V. Good language models have much lower perplexity.
