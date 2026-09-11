# Data Card — Fake and Real News Dataset (ISOT)

## Dataset Summary
This project uses the "Fake and Real News Dataset" (ISOT Fake News Detection
Dataset), sourced from Kaggle (uploaded by clmentbisaillon), originally compiled
by the University of Victoria's ISOT Research Lab. It consists of two CSV files:
`Fake.csv` and `True.csv`, containing full news articles labeled as fake or real
respectively.

## Source and Provenance
- Platform: Kaggle
- Original compiler: ISOT Research Lab, University of Victoria
- Access route: Public download via Kaggle (no scraping performed by the author)
- License: Per Kaggle listing terms; used here for academic, non-commercial
  coursework purposes only

## Composition
- `Fake.csv`: 23,481 news articles labeled as fake/misinformation
- `True.csv`: 21,417 news articles labeled as legitimate/real
- Total: 44,898 articles (52.3% fake / 47.7% real — approximately balanced)
- Columns: `title`, `text` (article body), `subject`, `date`

## Collection Process
The dataset was compiled by the original researchers from various news
websites and fact-checking sources (real articles largely from Reuters; fake
articles flagged by fact-checking organizations). The author of this project
did not collect any new data.

## Intended Use
This dataset is used to build and compare a classical (TF-IDF + Logistic
Regression) baseline against an embedding-based approach for misinformation-
style text classification, as part of a Ghana/Africa-context academic
research exercise (DCIT 316 Final Individual Research Project, University of
Ghana).

## Known Limitations
- The dataset is US-centric in topic and sourcing (not African/Ghanaian
  social media text); findings should not be generalized to Ghanaian
  misinformation without further validation
- It contains full news articles, not short social-media-style posts, which
  differs from the typical "social media mining" text format
- Labeling reflects the original compilers' fact-checking judgments at time
  of collection; it is not independently re-verified in this project
- No demographic or author metadata is available for bias auditing

## Ethical Considerations
No personal or private data is included. The dataset does not identify
individual social media users. This project does not scrape or collect any
new data from social platforms, in line with course ethics requirements.