# Surgical Site Infection Risk After Colon Surgery in California Hospitals (2024)

[![License: CC-BY-NC-4.0](https://img.shields.io/badge/License-CC--BY--NC--4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

Hospital-level SSI data are sparse, particularly for low-volume facilities, making naive risk estimates unreliable. This project estimates facility-level SSI risk following colon procedures in California hospitals (2024), using hierarchical Bayesian modeling to produce stable estimates through partial pooling across facilities and counties.

## Tools and Methods

**Methods:** Hierarchical Bayesian binomial models with partial pooling for facility- and county-level effects. Compared against logistic regression, non-hierarchical Bayesian binomial models, and GLMMs to illustrate what pooling recovers and where flat models break down.

**Tools:** R · JAGS · ggplot2 · plotly · tidyverse · MyST Markdown · LaTeX

> **Manuscript-Style Summary Available:**  
> For a concise, manuscript-quality summary of this project, including abstract, full introduction, methods, results, and conclusions formatted in LaTeX, see [the report PDF](latex/20260115_example_report.pdf). The report focuses on the final hierarchical model and is formatted for publication.

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
├── latex/                            # LaTeX manuscript-style report
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