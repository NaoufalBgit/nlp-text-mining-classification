# 🌬️ NLP Text Mining & Classification – Wind Accident Corpus (ARIA)

End-to-end NLP pipeline for text mining and classification on a French corpus of wind turbine accident reports from the ARIA database.

## Overview

This project implements a complete NLP pipeline applied to 285 accident reports related to wind turbines, sourced from the French ARIA database. The pipeline covers linguistic preprocessing, morphosyntactic analysis, named entity recognition, term extraction, semantic relation acquisition, and multi-label text classification.

## Features

- **Corpus Analysis**: Word count, sentence count, vocabulary size per document and globally
- **Text Preprocessing**: Tokenization, lemmatization, POS tagging using spaCy, TreeTagger and FLEMM
- **Text Classification**: Multi-class classification of accident consequences using TF-IDF, n-grams, lemmas and morphosyntactic features
- **Named Entity Recognition**: Temporal expressions (HeidelTime), distances, speeds, animal species, wind turbine components and protection devices (Brat annotations)
- **Term Extraction**: Automatic term extraction using YaTeA, term recognition from domain-specific resources (TermTagger)
- **Semantic Relations**: Hypernymy relation acquisition via lexical inclusion and lexico-syntactic patterns
- **Evaluation**: 10-fold cross-validation, macro F1-score, inter-annotator agreement (Cohen's Kappa)

## Technologies Used

| Category | Tools |
|---|---|
| NLP | spaCy, NLTK, TreeTagger, FLEMM |
| Annotation | Brat, HeidelTime |
| Term Extraction | YaTeA, TermTagger |
| Classification | scikit-learn (SVM, TF-IDF, n-grams) |
| Data | pandas, NumPy |
| Language | Python, Shell |

## Dataset

- **Source**: ARIA database (French Ministry of Ecology)
- **Corpus**: 285 accident reports related to wind turbines
- **Format**: Raw text files (`.txt`) + structured metadata (`.csv`)
- **Language**: French

### Metadata fields include:
- Date and location of the accident
- Type and class of accident
- Causes and consequences
- Human, environmental and economic impact

## Project Structure

```
nlp-text-mining-classification/
├── notebooks/
│   ├── 01_corpus_analysis.ipynb          # Corpus statistics (word/sentence count)
│   ├── 02_preprocessing_classification.ipynb  # TF-IDF, n-grams, classification
│   ├── 03_pos_tagging_lemmatization.ipynb     # spaCy, TreeTagger, FLEMM
│   ├── 04_annotation_ner.ipynb               # HeidelTime, Brat, NER
│   ├── 05_term_extraction.ipynb              # YaTeA, TermTagger
│   ├── 06_semantic_relations.ipynb           # Hypernymy acquisition
│   └── 07_final_classification.ipynb         # Full pipeline, evaluation
├── .gitignore
└── README.md
```

## Pipeline Overview

1. **Corpus Analysis** – Word/sentence count per document and globally, vocabulary size
2. **Preprocessing & Classification** – TF-IDF, n-grams, lemmas, POS tags → multi-class classification of accident consequences
3. **Morphosyntactic Tagging** – spaCy, TreeTagger, FLEMM comparison
4. **Annotation & NER** – Manual annotation with Brat, temporal NE recognition with HeidelTime, distance/speed extraction
5. **Term Extraction** – Automatic extraction with YaTeA, recognition from wind turbine and animal terminology
6. **Semantic Relations** – Hypernymy via lexical inclusion and lexico-syntactic patterns
7. **Final Classification** – Combining all features (lemmas, POS, terms, NER, semantic relations) for best macro F1-score

## Evaluation

Models are evaluated using:
- **Macro F1-score** (primary metric)
- **Precision & Recall**
- **10-fold cross-validation**
- **Cohen's Kappa** (inter-annotator agreement)

## Installation

```bash
pip install pandas numpy scikit-learn spacy nltk
python -m spacy download fr_core_news_sm
```

> **Note**: Some tools (TreeTagger, FLEMM, HeidelTime, YaTeA, Brat) require a specific Linux environment and are pre-installed on the course virtual machine.

## Author

**Naoufal Benamar** – [GitHub](https://github.com/NaoufalBgit) | [LinkedIn](https://www.linkedin.com/in/naoufal-benamar-97217b1a4/)
