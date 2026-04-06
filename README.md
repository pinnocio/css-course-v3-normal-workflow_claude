# Computational Social Science: A Graduate & Undergraduate Course

[![Render Site](https://github.com/YOUR_USERNAME/css-course/actions/workflows/render-site.yml/badge.svg)](https://github.com/YOUR_USERNAME/css-course/actions)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

A fully open-source, interactive RMarkdown course in **Computational Social Science** covering quantitative, qualitative, and mixed methods. Designed for both **undergraduate** and **graduate** students across sociology, political science, psychology, public health, communication, criminology, geography, and economics.

---

## Course Structure

| Module | Topic | Key Methods | Primary Packages |
|--------|-------|-------------|-----------------|
| 01 | Epistemology & Foundations | CSS Overview, Research Ethics | `gssr`, `tidyverse` |
| 02 | Qualitative & Mixed Methods | CGT, QCA, Coding | `tidytext`, `QCA` |
| 03 | Measurement: EFA & CFA | Factor Analysis, Invariance | `psych`, `lavaan` |
| 04 | SEM & Causal Inference | Path Models, DAGs, DiD | `lavaan`, `dagitty`, `did` |
| 05 | Latent Class & Profile Analysis | LCA, LPA, RCA, GoM, Q-Method | `poLCA`, `tidyLPA`, `corclass` |
| 06 | Text Analysis | LDA, STM, Embeddings, BERT | `quanteda`, `stm`, `text2vec` |
| 07 | Network Analysis | Centrality, Communities, ERGM | `igraph`, `statnet` |
| 08 | Spatial Social Science | GIS, LISA, Spatial Regression | `sf`, `spdep`, `tidycensus` |
| 09 | Integration | Multi-method Design | All of the above |

---

## Dual-Track Design

Every module contains **two parallel tracks**:

- 🟦 **Undergraduate Track** — Conceptual clarity, guided code templates, interpretation focus
- 🟥 **Graduate Track** — Theoretical depth, methodological critique, open-ended pipelines

---

## Prerequisites

### Software
- [R](https://cran.r-project.org/) (≥ 4.3.0)
- [RStudio](https://posit.co/download/rstudio-desktop/) (≥ 2023.06)
- [Git](https://git-scm.com/)

### R Packages — Install Everything at Once

```r
source("R/install_packages.R")
```

Or manually:

```r
install.packages(c(
  # Core
  "tidyverse", "here", "rmarkdown", "knitr", "kableExtra", "patchwork",
  # Data access
  "haven", "readxl", "jsonlite",
  # GSS & ANES
  "devtools",
  # Factor analysis & SEM
  "psych", "GPArotation", "lavaan", "semPlot", "semTools",
  # Causal inference
  "dagitty", "ggdag", "mediation", "did", "rdrobust", "MatchIt",
  # Latent class
  "poLCA", "tidyLPA", "mclust",
  # Text analysis
  "quanteda", "quanteda.textplots", "quanteda.textstats",
  "topicmodels", "stm", "tidytext", "text2vec", "tm",
  # Networks
  "igraph", "igraphdata", "tidygraph", "ggraph", "statnet",
  "ergm", "intergraph",
  # Spatial
  "sf", "spdep", "spatialreg", "tidycensus", "tigris", "tmap", "viridis",
  # QCA
  "QCA", "SetMethods"
))

# GitHub packages
devtools::install_github("kjhealy/gssr")
devtools::install_github("jamesmartherus/anesr")
devtools::install_github("iqss/dataverse-client-r")
install.packages("corclass")   # Correlational Class Analysis
```

---

## Getting Started

### Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/css-course.git
cd css-course
```

### Open the project

Double-click `css_course.Rproj` in RStudio.

### Install packages

```r
source("R/install_packages.R")
```

### Download data

```r
source("R/download_data.R")
```

### Render the full site

```r
rmarkdown::render_site()
```

Or render a single module:

```r
rmarkdown::render("modules/module_01_foundations.Rmd")
```

---

## Repository Structure

```
css-course/
├── css_course.Rproj        # RStudio project file
├── _site.yml               # Website navigation config
├── index.Rmd               # Course homepage
├── README.md               # This file
│
├── modules/                # 9 lecture RMarkdown files
│   ├── module_01_foundations.Rmd
│   ├── module_02_qualitative.Rmd
│   ├── module_03_efa_cfa.Rmd
│   ├── module_04_sem_causal.Rmd
│   ├── module_05_latent.Rmd
│   ├── module_06_text.Rmd
│   ├── module_07_networks.Rmd
│   ├── module_08_spatial.Rmd
│   └── module_09_integration.Rmd
│
├── exercises/              # Student exercise files (no solutions)
│   ├── ex_01_foundations.Rmd
│   ├── ex_02_qualitative.Rmd
│   ├── ex_03_efa_cfa.Rmd
│   ├── ex_04_sem_causal.Rmd
│   ├── ex_05_latent.Rmd
│   ├── ex_06_text.Rmd
│   ├── ex_07_networks.Rmd
│   └── ex_08_spatial.Rmd
│
├── solutions/              # Instructor solution keys
│   ├── solutions_index.Rmd
│   ├── sol_01_foundations.Rmd
│   └── ...
│
├── R/                      # Shared utility scripts
│   ├── install_packages.R
│   ├── download_data.R
│   ├── theme_css.R         # Custom ggplot2 theme
│   └── helpers.R
│
├── data/
│   ├── raw/                # Downloaded raw data (gitignored)
│   └── processed/          # Cleaned/processed data
│
├── figures/                # Saved plots
├── docs/                   # Rendered HTML site (GitHub Pages)
└── .github/
    └── workflows/
        └── render-site.yml # Auto-render on push
```

---

## Data Sources

All datasets are publicly available and free. The `R/download_data.R` script automates access where possible.

| Dataset | Source | Modules |
|---------|--------|---------|
| General Social Survey (GSS) | [NORC](https://gss.norc.org/) | 01, 03, 05 |
| ANES 2020 Time Series | [electionstudies.org](https://electionstudies.org/) | 01, 04, 05 |
| IPIP Big Five (bfi) | [openpsychometrics.org](http://openpsychometrics.org/_rawdata/) | 03 |
| World Values Survey Wave 7 | [worldvaluessurvey.org](https://www.worldvaluessurvey.org/) | 03, 05 |
| UN General Debate Corpus | [Harvard Dataverse](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/0TJX8Y) | 06 |
| US Inaugural Addresses | Built into `quanteda` | 06 |
| Zachary's Karate Club | Built into `igraphdata` | 07 |
| Florentine Families | Built into `ergm` | 07 |
| ACS via Census API | [data.census.gov](https://data.census.gov) | 08 |

---

## Citing This Course

If you use or adapt this material:

```
Author(s). (2025). Computational Social Science: A Graduate & Undergraduate Course.
GitHub. https://github.com/YOUR_USERNAME/css-course
```

---

## License

Course materials: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — freely share and adapt with attribution.
Code: [MIT License](LICENSE.md)

---

## Contributing

Pull requests welcome. Please open an issue first for major changes.

---

## Contact

For questions, open a GitHub Issue.
