---
title: "Two-layer hierarchical time-to-event conformal prediction"
excerpt: "Developing marginal and covariate-adaptive lower prediction bounds for clustered survival data with right censoring."
collection: portfolio
permalink: /portfolio/two-layer-hierarchical-conformal-prediction/
portfolio_order: 1
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

### Conditional conformal prediction extension

Marginal coverage is an important starting point, but it can hide systematic differences across clinically or operationally meaningful groups. A procedure may achieve its target coverage on average while producing bounds that are too optimistic for one hospital, risk group, age range, or covariate region and unnecessarily conservative for another. The conditional extension asks a more local question: **can the lower prediction bound adapt to the observed characteristics of a new cluster or individual while retaining a transparent coverage guarantee?**

The current extension conditions calibration on cluster- and individual-level information without treating observations within the same cluster as independent. Progress to date includes:

- defining cluster-conditional and covariate-adaptive prediction targets separately from the original marginal target;
- formulating a robust conditional LPB that allows the calibration distribution to change across relevant covariate regions;
- developing candidate local and weighted calibration rules that preserve cluster-level influence rather than allowing large clusters to dominate;
- identifying the overlap, positivity, and effective-sample-size conditions needed for conditional calibration to remain informative;
- clarifying the tradeoff between stronger conditional guarantees and wider, more conservative prediction bounds; and
- designing simulation settings that vary censoring, within-cluster dependence, cluster-size imbalance, and covariate shift.

The main theoretical work now is to determine which conditional statements can be supported in finite samples and which require approximate, group-conditional, or PAC-style formulations. This distinction is essential: exact distribution-free conditional coverage is generally too strong without additional structure, so the goal is a useful guarantee whose assumptions and limitations are explicit.

### Current progress

The project has progressed from literature review and notation design to candidate algorithms, theorem-level analysis, and a concrete plan for computational evaluation. The marginal hierarchical framework and the conditional extension now have separate prediction targets, calibration logic, and assumption sets. Current work includes:

- completing the proof structure for cluster-level and individual-level lower bounds under right censoring;
- checking when focused and weighted calibration remain valid after conditioning or covariate-based selection;
- developing population, group-conditional, and PAC-style coverage arguments for the conditional extension;
- translating each theoretical target into an implementable calibration algorithm;
- comparing the framework with full-survival-distribution calibration methods; and
- implementing simulation studies to measure marginal and subgroup coverage, LPB width, conservativeness, and sensitivity to censoring and cluster imbalance.

The research is ongoing. The aim is not only to propose an algorithm, but also to state clearly what can and cannot be guaranteed under realistic hierarchical survival-data assumptions.

### Inspiration and real-world applications

The project is motivated by a gap between how prediction guarantees are usually reported and how decisions are actually made. A clinician, hospital, regulator, or operations team rarely asks whether a method works well for an average observation pooled across every setting. They want to know whether the bound remains trustworthy for a patient with particular characteristics, treated within a particular type of institution, under the censoring and dependence patterns present in their data.

One natural application is multi-center healthcare data. Patients are nested within hospitals or clinics, and the outcome may be time to relapse, readmission, treatment failure, or another adverse event. A calibrated lower bound could summarize how long an event-free period is expected to last with a stated level of protection, supporting follow-up scheduling, resource planning, or risk stratification. The hierarchical framework prevents a few large hospitals from determining the calibration target, while the conditional extension seeks bounds that remain relevant for different patient and institutional profiles.

The same structure appears beyond medicine: component lifetimes are grouped by manufacturing site, students are nested within schools, households share environmental and socioeconomic factors, and repeated units are observed within geographic or operational sites. In each case, the practical need is similar: produce uncertainty statements that respect dependence, incomplete observation, and meaningful differences between groups rather than relying only on pooled average performance.

These bounds are intended as decision-support tools, not automatic clinical or operational rules. A real deployment would still require domain-specific validation, careful choice of covariates and prediction targets, and monitoring for changes in the data-generating process.

### Technical themes

Conformal prediction, conditional and group-conditional coverage, survival analysis, right censoring, hierarchical and clustered data, lower prediction bounds, weighted and local calibration, covariate shift, finite-sample coverage, and PAC-style guarantees.
