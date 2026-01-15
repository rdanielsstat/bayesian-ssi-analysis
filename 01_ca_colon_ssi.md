---
title: Introduction and Background
subject: Background
subtitle: Surgical site infection risk following colon procedures in California hospitals (2024)
exports: 
  - format: pdf
    template: curvenote
    # template: arxiv_two_column # requires abstract
  # - format: pdf+tex
keywords: [surgical site infection, colon surgery, hospital quality, healthcare-associated infections, California hospitals, epidemiology, risk modeling]
---

:::{seealso}
For a manuscript-quality summary of this project, including abstract, introduction, methods, results, and conclusions formatted in LaTeX, see [this report](latex/20260115_example_report.pdf). This abridged write-up presents the same analysis in a concise, narrative format, highlighting the manuscript-ready presentation of the work.
:::

Surgical site infections (SSIs) are complications of surgery that account for 20–31% of all hospital-acquired infections (HAIs) and substantially increase patient morbidity, mortality, and hospitalization costs [@nhsn2026ssi]. After colorectal surgery, it has been estimated that 4.2% of patients develop SSIs, resulting in longer hospital stays and higher costs [@gantz2019].

Many hospitals report zero or only a small number of infections, which makes SSI data particularly noisy. The goal of this project is to use 2024 [California SSI data](https://data.chhs.ca.gov/dataset/surgical-site-infections-ssis-for-28-operative-procedures-in-california-hospitals) to estimate facility-level SSI risk for colon procedures, accounting for facility type and county-level contextual factors [@cdph2024ssi]. I address the following primary questions:

1. What are the posterior estimates of SSI risk for each facility, and how do these differ from the observed rates once uncertainty and partial pooling are considered?
2. How much do SSI risks vary across counties after adjusting for facility type, as quantified by the posterior distribution of county-level random effects?

To answer these questions, I fit a Bayesian hierarchical binomial model, which allows facilities within the same county to share information while capturing meaningful differences across facilities and counties. The model produces partially pooled estimates of SSI risk with full posterior uncertainty, providing a more stable and interpretable representation than raw observed rates, particularly for low-volume facilities.

Along the way, I also fit and evaluate several simpler models, including a standard logistic regression, a non-hierarchical Bayesian binomial model, and a generalized linear mixed model (GLMM). These models serve two purposes: to provide baseline comparisons for inference and prediction, and to illustrate the limitations of approaches that do not fully account for multilevel structure and small-sample variability. Together, these comparisons motivate the use of hierarchical Bayesian modeling as a principled framework for facility-level risk estimation in sparse and heterogeneous healthcare data.