## LaBSE and Its Relevance for Medieval Multilingual Corpora 

### What is LaBSE?

Language-Agnostic BERT Sentence Embedding (LaBSE) is a multilingual sentence embedding model designed to map sentences from different languages into a shared semantic vector space. It is trained using large-scale parallel corpora and optimized with translation-ranking and contrastive learning objectives, enabling it to capture semantic similarity across languages.

In this framework, semantically equivalent sentences in different languages are embedded closely together, while unrelated sentences are pushed apart. This makes LaBSE particularly effective for tasks such as cross-lingual retrieval, bitext mining, and multilingual semantic similarity.

---

### Why Use LaBSE for This Corpus?

The corpus constructed in this study consists of parallel medieval texts in multiple languages, characterized by significant variation in syntax, lexicon, and translation practices.

LaBSE is particularly well suited for this setting because:

- it does not rely on strict lexical overlap,
- it is robust to syntactic variation,
- it can capture semantic equivalence across non-literal translations.

These properties make it an appropriate model for aligning and representing medieval multilingual material, where translations are often approximate, interpretative, or structurally divergent.

---

### Why Fine-Tune LaBSE on Medieval Texts?

Although LaBSE is trained on large modern multilingual corpora, it is not optimized for pre-modern language varieties. Medieval texts present several challenges:

- orthographic variation,
- archaic vocabulary,
- non-standardized grammar,
- non-literal and adaptive translation practices.

As a result, the semantic representations produced by the base model may be suboptimal for this domain.

Fine-tuning LaBSE on a carefully curated medieval parallel corpus allows the model to:

- adapt to historical linguistic variation,
- improve alignment across medieval language forms,
- better capture domain-specific semantic relations.


By fine-tuning the model on medieval textual material, this process encourages it to capture **historically grounded cross-lingual correspondences**, thereby improving performance on downstream tasks involving medieval texts.

---

### Design Implication

Given the contrastive learning framework of LaBSE, the quality of sentence pairs used for fine-tuning is critical. The model assumes that each pair represents a true semantic equivalence. Therefore, the construction of the corpus emphasizes:

- precise semantic alignment,
- coherent segmentation,
- and minimal noise.

This motivates the data curation strategy adopted in this work.


----
## Why Data Quality Matters

LaBSE maps semantically equivalent sentences across languages close together in a shared vector space. Because it learns from aligned sentence pairs, the quality of these pairs is crucial: noisy or poorly aligned data can provide misleading training signals and degrade the resulting embeddings.

Data quality ≠ data quantity

✔ Clean, well-aligned corpus → strong training signal

❌ Large, noisy corpus → weak or misleading signal