# Analysing-Online-Health-Information-Using-Natural-Language-Processing
## Overview
This project evaluates the consistency of health-related claims by comparing them with trusted reference texts using Natural Language Processing (NLP) techniques.

The system combines:
- TF-IDF (lexical similarity)
- Sentence-BERT (semantic similarity)
- Score-based ensemble classification

## Methodology
The pipeline consists of:

1. Data collection from PUBHEALTH dataset (claims)
2. Reference dataset from NHS and WHO sources
3. Text preprocessing (cleaning, normalization)
4. Similarity modelling:
   - TF-IDF cosine similarity
   - SBERT cosine similarity
5. Ensemble scoring:
   Ensemble Score = (TF-IDF + SBERT) / 2
6. Threshold-based classification:
   - Consistent: score ≥ 0.43
   - Partially aligned: 0.34 ≤ score < 0.43
   - Inconsistent: score < 0.34

## Evaluation
- Development set: 45 labelled pairs (threshold tuning)
- Held-out test set: 18 labelled pairs

### Final Results (Test Set)
- Accuracy: 0.611
- Macro F1-score: 0.602

### Key Findings
- TF-IDF performs better than SBERT individually
- Ensemble approach achieves best performance
- Partially aligned class is the most challenging

## Files Included
- Main implementation script / notebook
- Evaluation datasets (sample)
- Code for similarity modelling and classification

## Note
This project assesses alignment between claims and references and does not perform full factual verification.
