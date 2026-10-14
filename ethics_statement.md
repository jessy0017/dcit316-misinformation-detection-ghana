# Ethics Statement

## Data
- This project uses the ISOT Fake and Real News Dataset, a public benchmark
  downloaded from Kaggle. No data was scraped or collected from any social
  media platform.
- The dataset contains published news articles. It contains no personal or
  private user data and does not identify individual social media users.
- The raw CSV files are not stored in this repository. The README and
  data_card.md explain how to download them.

## Risks and Limitations
- **Misclassification:** the models can label real articles as fake and fake
  articles as real. In the artifact-stripped baseline, 116 fake articles
  were labelled real and 61 real articles were labelled fake.
- **Inflated accuracy:** the dataset has two label leaks (the `subject` field
  and the "(Reuters)" string), so reported accuracy overstates real-world
  performance. See Sections 3.2 and 6.1 of the paper.
- **Domain mismatch:** the data is US news articles from 2016-2017, not
  Ghanaian social media text. The results have not been validated for Ghana
  or Africa.
- **Labels not re-verified:** labels come from the original dataset
  compilers. No manual fact-checking was done in this project.
- **No bias audit:** the dataset has no author or demographic metadata, so
  fairness across groups was not evaluated.

## Intended Use
These models are for education and research only. They must not be used to
moderate content or to judge real people, outlets or posts. Any real-world
use would need human review and validation on locally representative data.

## AI Use
AI assistance was used in this project. See ai_use_disclosure.md.