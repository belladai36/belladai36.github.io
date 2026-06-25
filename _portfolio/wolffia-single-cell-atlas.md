---
title: "Prediction-first Wolffia single-cell atlas pipeline"
excerpt: "An end-to-end PIP-seq and cross-dataset prediction workflow for studying conserved, reduced, or compressed cell programs in Wolffia australiana."
collection: portfolio
permalink: /portfolio/wolffia-single-cell-atlas/
portfolio_order: 1
---

*Wolffia australiana* is one of the world's smallest and most morphologically simplified flowering plants. This project asks whether that organism-level simplification is also reflected in its cellular and transcriptional organization.

I developed a reproducible, end-to-end workflow for future *Wolffia* PIP-seq data. The pipeline begins with per-cell FASTQ files and covers:

- FastQC and MultiQC read-quality assessment
- STAR alignment and featureCounts gene quantification
- gene-by-cell matrix construction
- cell-level quality control and filtering
- normalization, highly variable gene selection, and PCA
- Leiden clustering and UMAP visualization
- marker discovery and conservative cell-state annotation
- PAGA trajectory inference and parameter-robustness checks

Because the primary *Wolffia* data are still being prepared, I also built a prediction-first reference framework using public plant single-cell datasets. The workflow resolves marker genes across gene-symbol and Arabidopsis locus-ID formats, scores broad biological programs, trains statistical classifiers, and evaluates cross-dataset label transfer.

Initial validation on public Arabidopsis datasets showed that the pipeline can recover and transfer broad transcriptional structure across experiments. This establishes a cautious proof of concept for testing whether canonical flowering-plant programs are preserved, weakened, merged, or absent in *Wolffia*.

### Technologies

Python, R, Scanpy, AnnData, scikit-learn, STAR, featureCounts, FastQC, MultiQC, shell scripting, YAML, and public GEO single-cell datasets.

### Project repository

- [View the code, documentation, and analysis workflow on GitHub](https://github.com/belladai36/wolffia-single-cell-atlas-pipeline)
