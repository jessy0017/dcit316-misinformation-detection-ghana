# Misinformation Detection in Ghanaian Social Media Discourse
### DCIT 316 Final Individual Research Project — Computational Models for Social Media Mining
University of Ghana, Department of Computer Science

## Overview
This project investigates misinformation-style text classification using
the ISOT Fake and Real News Dataset, comparing a classical TF-IDF +
Logistic Regression baseline against an embedding-style TF-IDF + SVD
approach. A central focus of this project is artifact-aware evaluation:
identifying and quantifying dataset-specific shortcuts (label leaks) that
can inflate reported model performance, rather than treating benchmark
accuracy at face value.

## Key Findings
- Identified a near-perfect label leak via the `subject` metadata field
- Identified a 99.2%/0.04% label leak via the "(Reuters)" source-attribution
  string in article text
- Classical TF-IDF baseline: 98.68% accuracy (with artifact) / 98.00%
  (artifact-stripped)
- Embedding-style (TF-IDF+SVD) model: 96.55% accuracy
- Quantified error analysis of 156 disagreement cases between the two
  models, linking classifier disagreement to sensationalist headline style

See `paper/` for the full research paper and `reports/metrics.json` for
complete numerical results.

## Repository Structure
├── data/raw/ # Fake.csv, True.csv (not tracked in git — see Data below)
├── notebooks/
│ └── 01_eda_and_baseline.ipynb # Full analysis: EDA, preprocessing,
│ # baseline, embedding comparison, error analysis
├── reports/
│ ├── figures/ # All generated charts and confusion matrices
│ ├── metrics.json # Structured results
│ ├── model_comparison.csv
│ └── disagreement_cases.csv
├── paper/
│ └── final_paper.pdf # Full research paper (PDF)
├── data_card.md
├── model_card.md
├── ethics_statement.md
├── literature_matrix.md
├── failure_log.md
├── reproducibility_checklist.md
├── ai_use_disclosure.md
├── requirements.txt
└── README.md


## Data
This project uses the ISOT Fake and Real News Dataset, publicly available
on Kaggle ("fake-and-real-news-dataset" by clmentbisaillon). Due to file
size, the raw CSVs (`Fake.csv`, `True.csv`) are not tracked in this
repository. To reproduce:

1. Download the dataset from Kaggle:
   https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset
2. Place `Fake.csv` and `True.csv` into `data/raw/`

See `data_card.md` for full dataset documentation, provenance, and known
limitations.

## Reproducing the Analysis
1. Clone this repository
2. Install dependencies:

pip install -r requirements.txt

3. Download the dataset as described above
4. Open `notebooks/01_eda_and_baseline.ipynb` and run all cells in order
   (Kernel → Restart Kernel and Run All Cells)

All figures and metrics will regenerate into `reports/`.

## Documentation
- `data_card.md` — dataset description, provenance, limitations
- `model_card.md` — model details, results, error analysis, ethical
  considerations
- `ethics_statement.md` — ethical considerations for this project
- `ai_use_disclosure.md` — disclosure of AI tool usage during this project

## Author
Jessica Zunuo Puozaa, University of Ghana, Level 300 Computer Science

