---
title: "Cross-species single-cell mapping with SAMap"
excerpt: "A comparative single-cell analysis linking Pristina gut cell states with other organisms, alongside local SAMap development for finer pattern discovery."
collection: portfolio
permalink: /portfolio/samap-cross-species-gut-comparison/
portfolio_order: 3
---

This project extends my single-cell analysis work from building a *Wolffia* atlas pipeline to asking a broader comparative question: how can cell states in *Pristina* be mapped against other organisms, such as human and zebrafish, in a statistically careful and biologically interpretable way?

The first part of the project uses **SAMap** to compare single-cell expression patterns across species. I focus on gut-related cell populations and examine whether local transcriptional neighborhoods in *Pristina* show similarity to reference structures in other organisms. The analysis emphasizes feature harmonization, cross-species alignment, similarity scoring, and cautious interpretation of conserved versus organism-specific signals.

The second part develops a **local SAMap workflow** for more focused pattern discovery. Instead of relying only on global cross-species alignment, this component builds a local analysis framework that can inspect smaller neighborhoods, candidate cell groups, and region-specific similarities. The goal is to make SAMap-style comparison more useful for targeted biological questions, especially when the relevant signal is local, sparse, or partially obscured by broader organism-level differences.

### Main components

- comparative single-cell mapping between *Pristina* and other organisms including human and zebrafish
- SAMap-based alignment and similarity analysis across species
- local SAMap workflow development for targeted pattern discovery
- feature harmonization and cross-dataset preprocessing
- interpretation of conserved, diverged, and locally enriched transcriptional patterns
- reproducible code organization for exploratory cross-species analysis

### Statistical and computational themes

This work connects high-dimensional statistical learning with comparative genomics. The central challenge is not only to compute an alignment, but also to evaluate whether the resulting similarities are stable, interpretable, and meaningful across datasets with different species, technologies, annotations, and sample structures.

### Project repositories

- [View the comparative SAMap gut analysis repository](https://github.com/belladai36/samap-gut-comparison)
- [View the local SAMap development repository](https://github.com/belladai36/SAMap_localpattern)
