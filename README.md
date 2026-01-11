# Surgical Site Infection Risk After Colon Surgery in California Hospitals (2024)

[![License: CC-BY-NC-4.0](https://img.shields.io/badge/License-CC--BY--NC--4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

This repository contains the data, analyses, and documentation for estimating facility-level surgical site infection (SSI) risk following colon procedures in California hospitals in 2024. The project employs hierarchical Bayesian modeling and complementary statistical methods to produce stable, interpretable estimates of hospital-specific and county-specific SSI risk.

## Project Overview

Surgical site infections (SSIs) are a major source of postoperative complications, morbidity, and healthcare costs. Hospital-level SSI data are often sparse, particularly for low-volume facilities, leading to noisy estimates of risk. This project focuses on:

1. Estimating facility-level SSI risk using hierarchical Bayesian models that account for both facility type and county-level effects.
2. Comparing hierarchical Bayesian results with alternative approaches, including:
   - Standard logistic regression
   - Non-hierarchical Bayesian binomial modeling
   - Generalized linear mixed models (GLMMs)

The project includes four main analyses:

1. **Introduction and Background** – Overview of SSIs, data source, and research questions.
2. **Data Exploration** – Summary and visualization of facility-level SSI rates and related covariates.
3. **Non-Hierarchical Models** – Logistic and Bayesian binomial models without partial pooling.
4. **Hierarchical Models** – GLMM and hierarchical Bayesian models for partially pooled risk estimation.

## Tools and Methods

The analyses in this project use the following tools and frameworks:

- **[MyST Markdown / MyST-NB](https://mystmd.org/)** – For notebook-based reproducible workflows integrating Markdown, R, and LaTeX math.
- **[R](https://www.r-project.org/)** – Primary analysis environment.
- **[JAGS](https://mcmc-jags.sourceforge.io/)** – Bayesian computation and MCMC sampling.
- **[ggplot2](https://ggplot2.tidyverse.org/)** and **[plotly](https://plotly.com/r/)** – Data visualization and interactive graphics.
- **[tidyverse](https://www.tidyverse.org/)** – Data wrangling and manipulation.
- **Reproducible analytic workflow** – Analyses are conducted in MyST notebooks with code, commentary, and figures interleaved.
- **References/Citations** – Integrated with a BibTeX file (`references.bib`) to provide in-text citations and reference management.
- **Hierarchical Bayesian Modeling** – Partial pooling to stabilize estimates for low-volume hospitals and account for multilevel structure.
- **Generalized Linear Mixed Models (GLMMs)** – Facility- and county-level random effects for comparison with Bayesian hierarchical models.
- **Notebook & Markdown Integration** – Code, text, equations, and output are interleaved throughout the notebooks, providing clear documentation of the workflow.

## Repository Structure

```text
.
├── 01_ca_colon_ssi.md                # Intro and background section
├── 02_data.ipynb                     # EDA section
├── 03_non-hierarchical_models.ipynb  # Non-hierarchical models
├── 04_hierarchical_models.ipynb      # Hierarchical models
├── references.bib                    # BibTeX references
├── data/                             # Raw dataset (publicly available)
├── figures/                          # Generated figures from analyses
├── myst.yml                          # MyST project configuration
└── README.md                         # This file
```

## Data

Data for this analysis come from the **California Department of Health and Human Services (CHHS)** and are publicly available:

- [Surgical Site Infections (SSIs) for Operative Procedures in California Hospitals](https://data.chhs.ca.gov/dataset/surgical-site-infections-ssis-for-28-operative-procedures-in-california-hospitals)

The dataset includes facility-level SSI counts and procedure volumes, as well as facility type and county identifiers. No individual patient-level data are included.

## How to Reproduce the Analysis

1. Clone this repository:

```bash
git clone https://github.com/rdanielsstat/bayesian-ssi-analysis.git
cd bayesian-ssi-analysis
```

2. Install required R packages (example):
```r
install.packages(c("dplyr", "rjags", "ggplot2", "plotly", "IRdisplay", "kableExtra"))
```

3. Render notebooks to HTML or PDF via MyST (example):
```bash
myst build myst.yml
# or use Jupyter / VSCode to run notebooks interactively
```
This will generate HTML/PDF outputs in the `_build/` directory. Figures produced by the analysis are saved in the `figures/` subfolder.

## Citation

If you use this work in your research, please cite:

- Rob Daniels. _Hierarchical Modeling of Surgical Site Infection Risk After Colon Surgery in California Hospitals (2024)._ GitHub repository: https://rdanielsstat.github.io/bayesian-ssi-analysis.

## License

This repository is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/).

## Contact

Rob Daniels<br>
Email: rdanielsstat@gmail.com<br>
LinkedIn: https://www.linkedin.com/in/robcdaniels<br>
GitHub: [@rdanielsstat](https://github.com/rdanielsstat)<br>
Website: https://rdanielsstat.github.io