---
title: "Statistical learning for a Wolffia single-cell atlas"
excerpt: "A reproducible PIP-seq/Scanpy workflow combining dimension reduction, clustering, supervised classification, and cross-dataset label-transfer evaluation."
collection: portfolio
permalink: /portfolio/wolffia-single-cell-atlas/
portfolio_order: 2
---

*Wolffia australiana* is one of the world's smallest and most morphologically simplified flowering plants. This project asks whether that organism-level simplification is also reflected in its cellular and transcriptional organization.

I developed a reproducible statistical-computing workflow for future *Wolffia* PIP-seq data. The pipeline covers:

- cell-level quality control, filtering, and normalization
- highly variable feature selection and principal component analysis
- Leiden clustering and UMAP visualization
- marker-based feature assessment and conservative state annotation
- PAGA trajectory inference and parameter-sensitivity checks

Because the primary *Wolffia* data are still being prepared, I also built a prediction-first reference framework using public single-cell datasets. The workflow harmonizes features across datasets, constructs latent program scores, trains supervised classifiers, and evaluates cross-dataset label transfer.

Initial validation showed that the pipeline can recover and transfer broad structure across experiments. This provides a proof of concept while keeping the inferential limits of cross-dataset prediction explicit.

### Technologies

Python, R, Scanpy, AnnData, scikit-learn, PCA, Leiden clustering, UMAP, PAGA, supervised classification, Jupyter, Git/GitHub, and public single-cell reference datasets.

### Project repository

- [View the code, documentation, and analysis workflow on GitHub](https://github.com/belladai36/wolffia-single-cell-atlas-pipeline)
