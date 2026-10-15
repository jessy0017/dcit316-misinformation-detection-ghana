# Reproducibility Checklist

## Environment
- [x] Python 3.13
- [x] Packages listed in `requirements.txt`
- [x] Versions used: pandas 3.0.3, numpy 2.5.0, scikit-learn 1.9.0, matplotlib 3.11.0, seaborn 0.13.2, jupyter 1.1.1
- [ ] Versions are not pinned in `requirements.txt`

## Data
- [x] Public dataset: ISOT Fake and Real News (Kaggle, "fake-and-real-news-dataset")
- [x] Raw files are not stored in the repository (about 116 MB). Download steps are in `README.md` and `data_card.md`
- [x] Files go in `data/raw/` as `Fake.csv` and `True.csv`
- [x] No personal data, passwords or API keys in the repository

## Randomness
- [x] `random_state=42` for the shuffle, the train/test split, TruncatedSVD and Logistic Regression
- [x] Stratified split (`stratify=y`)

## Running it
- [x] Open `notebooks/01_eda_and_baseline.ipynb`
- [x] Run Kernel > Restart Kernel and Run All Cells
- [x] The notebook uses paths relative to `notebooks/`

## Outputs
- [x] `reports/metrics.json` and `reports/model_comparison.csv`
- [x] `reports/disagreement_cases.csv`
- [x] Figures in `reports/figures/` (class distribution, text length, subject by label, model comparison, three confusion matrices)

## Known limits
- [x] One train/test split, no cross-validation
- [x] No automated tests
- [x] Results on one dataset only