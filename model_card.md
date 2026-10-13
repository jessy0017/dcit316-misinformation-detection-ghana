# Model Card — Misinformation Detection (ISOT Dataset)

## Model Overview
Two models were built and compared for binary classification (fake vs. real)
of news articles from the ISOT Fake and Real News Dataset:

1. **TF-IDF + Logistic Regression (Classical Baseline)**
2. **TF-IDF + TruncatedSVD + Logistic Regression (Embedding-style Comparison)**

## Intended Use
Educational/research comparison of classical vs. embedding-style text
classification approaches for misinformation-style content, as part of
DCIT 316 (Computational Models for Social Media Mining), University of
Ghana. Not intended for production deployment or real-world misinformation
moderation.

## Training Data
- Source: ISOT Fake and Real News Dataset (see `data_card.md`)
- 44,228 articles after cleaning (670 near-empty rows removed)
- Features used: combined `title` + `text` (full_text)
- Explicitly excluded: `subject` (confirmed perfect label leak),
  `date` (not predictive of content)
- Train/test split: 80/20, stratified by label (random_state=42)

## Models and Results

| Model                                   | Accuracy | Macro F1 |
|------------------------------------------|----------|----------|
| TF-IDF Baseline (with Reuters artifact)   | 0.9868   | 0.9868   |
| TF-IDF Baseline (artifact stripped)       | 0.9800   | 0.9800   |
| Embedding-style (TF-IDF + SVD, 100 comps) | 0.9655   | 0.9655   |

TruncatedSVD explained variance ratio (100 components): 0.2016

## Key Finding: Dataset Artifact
99.2% of "real" articles contain the literal string "(Reuters)" versus
0.04% of "fake" articles — a near-total label leak tied to source
formatting rather than content. Removing this artifact only reduced
accuracy modestly (98.68% → 98.00%), suggesting the classifier retains
meaningful signal beyond this single marker, though other unexamined
dataset-specific artifacts may remain.

## Error Analysis
- 156 disagreement cases between the two models (1.76% of test set)
- The classical baseline was correct in 142 of these cases; the
  embedding-style model was correct in only 14
- 88 of 156 disagreement cases (56%) contained ALL-CAPS sensationalist
  markers in the first 200 characters, suggesting the baseline is more
  sensitive to stylistic/sensationalism cues than the SVD-compressed
  embedding representation, which appears to rely more on generic
  topical similarity

## Limitations
- Trained and evaluated only on US-centric news article text, not
  Ghanaian/African social media text; results should not be
  generalized without further validation on local data
- The embedding-style model uses TF-IDF + SVD as a proxy for semantic
  embeddings, not a genuine transformer-based embedding (e.g. BERT),
  which likely explains its comparatively low explained variance and
  weaker performance
- Dataset-specific artifacts beyond the identified Reuters marker may
  still inflate reported accuracy; results should be interpreted as an
  upper bound rather than a realistic real-world performance estimate

## Ethical Considerations
This model is not intended to make unilateral content moderation
decisions. Misclassification (particularly false negatives on genuine
misinformation) could cause real-world harm if deployed without human
oversight. No personal data is used or exposed.