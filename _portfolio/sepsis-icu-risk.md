---
title: "Sepsis ICU phenotyping and mortality prediction"
excerpt: "Discovering clinically distinct patient states and predicting hospital mortality from 274,844 four-hour ICU windows in MIMIC-III."
collection: portfolio
permalink: /portfolio/sepsis-icu-risk/
---

Sepsis patients are highly heterogeneous: people with the same diagnosis can differ sharply in organ dysfunction, treatment intensity, and mortality risk. This project combines unsupervised discovery and supervised prediction to study that heterogeneity using de-identified MIMIC-III critical-care data.

The analysis joins seven clinical tables into a panel of **274,844 four-hour windows from 8,668 ICU stays**. Features include vital signs, laboratory measurements, SOFA and SIRS scores, demographics, vasopressor and fluid administration, and mechanical ventilation.

### Methods

- Filtered heavily missing features while preserving informative missingness indicators
- Fit imputation, scaling, and dimensionality-reduction steps on training data only
- Split data by ICU stay to prevent repeated observations from leaking across train and test sets
- Used PCA, K-means, t-SNE, and UMAP to explore patient-state structure
- Compared logistic regression, random forest, gradient boosting, and neural-network mortality models
- Ran phenotype-stratified models and validity checks for leakage, model complexity, and treatment confounding

### Results

Clustering identified lower-acuity and higher-acuity patient states with clear differences in SOFA scores, ventilation, treatment intensity, and hospital mortality. The observed mortality rates were approximately **1.5% and 17.9%** across the two clusters.

Gradient boosting produced the strongest global held-out performance, with an **AUC of 0.877**. Cluster-stratified models also showed that prediction difficulty and important risk markers differed across patient states. These findings support subgroup-aware risk monitoring, but the analysis remains predictive and observational rather than causal.

![Clinical profiles of the two sepsis patient states](/images/projects/sepsis-cluster-profiles.png)

![Held-out predictive-model comparison](/images/projects/sepsis-model-comparison.png)

### Technologies

Python, pandas, NumPy, scikit-learn, PCA, K-means, t-SNE, UMAP, logistic regression, random forests, gradient boosting, neural networks, and MIMIC-III.

To protect patient privacy and follow responsible data-sharing practice, the underlying clinical CSV files are not published on this website.
