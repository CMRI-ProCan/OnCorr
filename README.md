# OnCorr: A pan-cancer mRNA-protein correlation tool for precision oncology

## Overview 

OnCorr is an interactive web tool for exploring the relationship between mRNA and protein abundance across multiple large-scale pan-cancer datasets. While transcriptomics is often used as a proxy for protein levels, mRNA–protein correlations vary widely across genes, tissues, and biological contexts. OnCorr makes this variability explicit by enabling users to systematically examine gene-specific correlations across multiple cohorts and tissue types.

The repository contains the code used for data processing, correlation analysis, and figure generation for the OnCorr manuscript.


## Repository structure 

```
├── analysis
├── code
├── data
│   ├── Datasets
│   │   └── CCLE
│   ├── OncoKb
│   ├── Pathways
│   └── Ranks
├── docs
│   ├── figure
│   │   ├── publication-figures.Rmd
│   │   └── supplementary-publication-figures.Rmd
│   └── site_libs
└── output
    ├── correlations-datasets
    └── Figures

```

**`analysis/`**:

Contains analysis scripts and notebooks used to explore mRNA–protein correlations, perform downstream statistical analyses, and generate intermediate results used in the manuscript.

**`code/`**:

Core functions and reusable code for data processing, correlation calculations, filtering, and annotation. These scripts underpin all analyses and figure generation in the repository.

**`data/`**:

Input data and reference resources used throughout the project, including processed datasets, pathway annotations, external knowledge bases, and ranked gene-level results required for analysis.

**`docs/`**:

R Markdown into html files and supporting assets used to generate publication and supplementary figures. This directory contains the source files for all figures reported in the manuscript.

**`output/`**:

Generated outputs from analyses, including correlation results and final figures. All files in this directory are derived from scripts in analysis/ and code/.


## How to regenerate figures or analysis 
All analyses and figures in the OnCorr manuscript can be reproduced using the code in this repository.

**Requirements**
Analyses were performed in R (≥ 4.2). Required R packages are listed within the analysis and figure-generation scripts. For full reproducibility, we recommend running the code in a clean R environment.

**Data**
Input datasets and reference resources are provided in the `data/` directory. These include pathway annotations from , external knowledge bases, and precomputed gene rankings from used throughout the analyses.

The processed transcriptomic and proteomic datasets can be retrieved from: 

| Dataset              | Proteomic location                         | Transcriptomic location                         |
|----------------------|--------------------------------------------|-------------------------------------------------|
| CCLE                 | [Nusinow et al](https://aus01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fgygi.hms.harvard.edu%2Fdata%2Fccle%2Fprotein_quant_current_normalized.csv.gz&data=05%7C02%7Cunawaz%40cmri.org.au%7Ca979c1bd500b4ede053608dc531fb561%7C67d2c49571004b968c22ce8f29840e03%7C0%7C1%7C638476642861499828%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&sdata=QlT08SZvfL2WawQQlTZFe4SX1UsWNBJ0QANE26iLlIc%3D&reserved=0)         |        [Nusinow et al](https://aus01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fgygi.hms.harvard.edu%2Fpublications%2Fccle.html&data=05%7C02%7Cunawaz%40cmri.org.au%7Ca979c1bd500b4ede053608dc531fb561%7C67d2c49571004b968c22ce8f29840e03%7C0%7C1%7C638476642861491155%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&sdata=nCR0jXke5%2BsP0qSKunq%2BzO7A1%2FVejnxH1x%2FRjRLbYrM%3D&reserved=0)   |
| CPTAC                | [LinkedOmicsKB](https://kb.linkedomics.org/download)          | [LinkedOmicsKB](https://kb.linkedomics.org/download)        |
| ProCan-DepMapSanger  | [Gonçalves et al](https://figshare.com/articles/dataset/Pan-cancer_proteomic_map_of_949_human_cell_lines/19345397)            | [Cell Model Passports](https://cellmodelpassports.sanger.ac.uk/downloads)  |



**Analysis**: 
All statistical analyses and correlation calculations are implemented in the `analysis/` directory. Running the scripts in `analysis/calculate-correlations.Rmd` will regenerate the correlation results written to `output/correlations-datasets`. Please ensure that the paths to input data are correctly specified before running the analysis. 

Figures
All manuscript and supplementary figures are generated from R Markdown documents located in `analysis/publication-figures.Rmd` and `analysis/supplementary-figures.Rmd`. Rendering these files will reproduce the figures saved to `output/Figures`.
