# Literature Matrix

| # | Source | What it did | Relevance to this project | Where used in the paper |
|---|--------|-------------|---------------------------|-------------------------|
| 1 | Ahmed, Traore & Saad (2017). Detection of online fake news using n-gram analysis and machine learning techniques. Springer. | Uses n-gram features and machine learning classifiers for fake news detection, on the ISOT dataset. | Source of the dataset used here. Real articles were crawled from Reuters.com, which explains the "(Reuters)" leak. | Related Work, Section 3 |
| 2 | Shu, Sliva, Wang, Tang & Liu (2017). Fake news detection on social media: A data mining perspective. ACM SIGKDD Explorations, 19(1). | Survey that frames fake news detection as a data mining problem (content, social context, propagation). | Frames this project as a content-based detection study. | Related Work |
| 3 | Wang (2017). "Liar, liar pants on fire": A new benchmark dataset for fake news detection. ACL. | Introduces the LIAR dataset of short political statements. | An alternative benchmark that I considered but did not use. | Related Work |
| 4 | Zhou & Zafarani (2020). A survey of fake news. ACM Computing Surveys, 53(5). | Survey of detection approaches (content, propagation, source). | Places this work in the content-based group. | Related Work |
| 5 | Pérez-Rosas, Kleinberg, Lefevre & Mihalcea (2018). Automatic detection of fake news. COLING. | Studies automatic fake news detection with classical classifiers. | Supports using TF-IDF with Logistic Regression as a baseline. | Related Work |
| 6 | Lee & Seung (1999). Learning the parts of objects by non-negative matrix factorization. Nature, 401. | Shows that matrix factorization can learn parts-based latent structure. | Course reading on factorization. The paper uses TruncatedSVD, a related but different decomposition, for the embedding-style model. | Related Work, Section 4.1 |
| 7 | Vespignani (2009). Predicting the behavior of techno-social systems. Science, 325. | Perspective on the limits of predicting behaviour in techno-social systems and the need for good data. | Supports the point that data collection can hide or create patterns. | Related Work |
| 8 | Dhar (2013). Data science and prediction. Communications of the ACM, 56(12). | Argues that predictive accuracy matters, and that models can pick up noise as well as signal. | Motivated checking what the model learned, and supports the finding that the simpler model did better. | Related Work, Discussion, Limitations |

## Gap this project addresses
The studies above report detection results on benchmark datasets. This project asks
how much of that performance survives once dataset-specific shortcuts (the `subject`
field and the "(Reuters)" string) are identified and removed.