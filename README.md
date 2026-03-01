# Companion Statistical Report (CSR) Template

A structured, versioned, executable document format for transparent statistical
reporting in experimental neuroscience, developed by the
**Bertrand Russell Research Excellence Group (NEC)**,
School of Medicine, Rio de Janeiro State University (UERJ).

---

## Overview

The Companion Statistical Report (CSR) is a supplementary document designed to
be submitted and reviewed alongside empirical neuroscience manuscripts. It
integrates data provenance, preprocessing decisions, exploratory analysis, model
specification, assumption diagnostics, inference with effect sizes, and
sensitivity analyses into a single executable document that makes every analytic
decision auditable and reproducible.

This repository contains the Quarto template that implements the CSR format,
along with institutional branding assets and rendering instructions.

---

## Repository Contents
```
CSReport/
├── StatReport_Template.qmd   # Main CSR template
├── StatReport_Template.pdf   # Knitted CSR template PDF
├── NEC_logo.jpeg             # Institutional logo (required for PDF rendering)
├── nec_params.tex            # Auto-generated at render time (do not edit)
└── README.md                 # This file
```

---

## Requirements

| Software | Version | Notes |
|---|---|---|
| [Quarto](https://quarto.org) | ≥ 1.8 | Stable release |
| [R](https://www.r-project.org) | ≥ 4.4.0 | Required for R workflows |
| [RStudio](https://posit.co/products/open-source/rstudio/) | ≥ 2024.12.0 | Recommended IDE |
| XeLaTeX | Any current TeX distribution | Required for PDF output |

### R packages

The following packages are loaded in the setup chunk and must be installed
before rendering:
```r
install.packages(c("tidyverse", "knitr", "kableExtra"))
```

Add any analysis-specific packages to the `setup` chunk of your working copy.

### Python (optional)

Python blocks are included throughout the template but set to `eval: false` by
default. To use Python, set your Quarto execution engine to Jupyter and activate
the relevant blocks:
```yaml
jupyter: python3
```

Python session information is captured automatically in the Session Information
section when enabled.

---

## Getting Started

### 1. Use this repository as a template

Click **Use this template** on GitHub to create a new repository for your
project. This preserves the template structure while giving you a clean
version history for your own work.

### 2. Edit the YAML parameters

Open `StatReport_Template.qmd` and update the `params` block at the top of
the file:
```yaml
params:
  manuscript_title:        "Your manuscript title here"
  principal_investigator:  "PI full name"
  statistical_analyst:     "Analyst full name"
  version_code:            "NECS01V01D0001"
  logo_path:               "NEC_logo.jpeg"
  confidentiality:         "Your confidentiality statement here."
```

Replace `NEC_logo.jpeg` with your own institutional logo if desired, or remove
the logo blocks from the title page and header if not applicable.

### 3. Render the document

From the terminal, in the directory containing the `.qmd` file:
```bash
quarto render StatReport_Template.qmd
```

Or use the **Render** button in RStudio.

The first render will generate `nec_params.tex` automatically. Do not edit this
file; it is overwritten on every render.

---

## Version Code Format

Each CSR is identified by a structured version code:
```
NECS  XX  V  XX  D  XXXX
 |    |      |      |
 |    |      |      Document iteration (4 digits)
 |    |      Version within service (2 digits)
 |    Service number (2 digits)
 NEC identifier
```

**Example:** `NECS01V03D0042` identifies service 01, version 03, document 42.

The version code is validated at compile time. Documents with malformed codes
will not render. This creates an auditable link between each analytical
iteration and its corresponding manuscript version.

---

## Template Sections

| Section | Purpose |
|---|---|
| About this document | Contextualizes the CSR and declares its scope |
| Analysis request and scope | States research questions and version-specific changes |
| Data provenance and preprocessing | Documents data origin and all preprocessing decisions |
| Exploratory data analysis | Characterizes distributions and data quality |
| Statistical models | Specifies model family, assumptions, and rationale |
| Inference and effect sizes | Reports estimates, confidence intervals, and effect sizes |
| Sensitivity analyses | Documents robustness to alternative analytic choices |
| Figures and tables | Self-contained reproducible code for all publication figures |
| Session information | Full computational environment record (R and/or Python) |

---

## Citation

If you use this template in your work, please cite the associated manuscript:

> Maria Clara Salgado Ramos, Alex Oliveira da Câmara, and Hercules Rezende Freitas.
> From Pipettes to P-Values: A Quarto Template for Companion Statistical Reporting in Experimental Neuroscience.
> (under peer-review).

---

## License

Creative Commons 4.0

---

## Contact

Bertrand Russell Research Excellence Group (NEC), Health Informatics Laboratory (LabInfoS)  
School of Medicine, Rio de Janeiro State University (UERJ)  
Rio de Janeiro, Brazil  
Email: [labinfos.uerj@gmail.com](labinfos.uerj@gmail.com)


*Issues and pull requests are welcome.*
