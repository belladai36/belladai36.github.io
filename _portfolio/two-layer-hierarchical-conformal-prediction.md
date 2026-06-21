---
title: "Two-layer hierarchical time-to-event conformal prediction"
excerpt: "Developing lower prediction bounds and finite-sample calibration strategies for clustered survival data with right censoring."
collection: portfolio
permalink: /portfolio/two-layer-hierarchical-conformal-prediction/
portfolio_order: 2
---

Many time-to-event datasets are not collections of independent individuals. Patients may be nested within hospitals, students within schools, repeated units within sites, or family members within households. Outcomes are dependent within each cluster, cluster sizes vary, and event times may be only partially observed because of right censoring. These features make standard individual-level conformal prediction difficult to apply directly.

This ongoing independent study develops a conformal-prediction framework for **two-layer hierarchical time-to-event data**. The central goal is to construct statistically valid and practically useful **lower prediction bounds (LPBs)** for future event times while respecting both the clustered sampling structure and the information lost through censoring.

### Statistical setting

The framework separates two sampling levels:

- a population of exchangeable clusters, and
- multiple potentially dependent individuals within each cluster.

This distinction matters because sampling a new cluster uniformly is different from sampling an individual uniformly from the pooled dataset. Large clusters would otherwise dominate calibration, changing the prediction target. The project therefore studies both cluster-level and individual-level targets and makes the weighting implied by each target explicit.

For time-to-event outcomes, the true event time may be unknown when an observation is censored. Calibration cannot simply treat every observed time as a completed event. A major part of the work is identifying conditions under which observable quantities provide conservative information about the unobserved miscoverage risk.

### Research questions

The project focuses on several connected questions:

- How should conformal scores be aggregated when observations are dependent within clusters?
- How can calibration give equal influence to clusters rather than unintentionally weighting by cluster size?
- What lower prediction bound can be justified when event times are right censored?
- Which guarantees follow from exchangeability and conditional independent censoring, and which require additional structural assumptions?
- How should guarantees differ for a new cluster, a new individual within a cluster, and covariate-shifted target populations?

### Methodological development

I have reviewed and synthesized literature on hierarchical conformal prediction, survival prediction, weighted calibration, focused conformal methods, and calibration of predicted survival distributions. Building on that foundation, I am developing:

- hierarchical empirical-risk formulations that preserve the intended cluster-level sampling target;
- focused calibration procedures using sufficiently observable individuals or clusters;
- individual-level and cluster-level lower-prediction-bound algorithms;
- conservative miscoverage bounds under right censoring;
- weighted extensions for covariate shift; and
- a pipeline that separates calibration of a base survival distribution from calibration of the final hierarchical LPB.

The analysis carefully distinguishes an exact coverage statement from a conservative upper bound on miscoverage. In particular, observability in survival data depends on event and censoring times, so exchangeability alone does not automatically justify every selected calibration set. The current work identifies the additional positivity, conditional-censoring, or dominance conditions needed for each claim.

### Current progress

The project has progressed from literature review and notation design to candidate algorithms and theorem-level analysis. Current work includes:

- refining the cluster-level and individual-level prediction targets;
- checking the assumptions required for focused calibration;
- developing population and PAC-style coverage arguments;
- comparing the framework with full-survival-distribution calibration methods; and
- planning simulation studies to evaluate coverage, conservativeness, cluster-size imbalance, and sensitivity to censoring.

The research is ongoing. The aim is not only to propose an algorithm, but also to state clearly what can and cannot be guaranteed under realistic hierarchical survival-data assumptions.

### Technical themes

Conformal prediction, survival analysis, right censoring, hierarchical and clustered data, lower prediction bounds, weighted calibration, covariate shift, finite-sample coverage, and PAC-style guarantees.
