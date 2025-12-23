# Survival Disparities in Andean Lymphoma Care (Quito, Ecuador)

This repository contains the complete analytical workflow and reproducibility scripts for the study: **"Universal coverage health system and survival disparities in Andean lymphoma care: a population-based analysis of 4,602 cases in Quito, Ecuador."**

## Project Overview

This study utilizes 23 years of population-based registry data (1996–2019) from the **National Tumor Registry (RNT)** of Quito. We analyze the rising burden of lymphoma and investigate how institutional entry points (MSP vs. IESS) and socioeconomic factors (education) impact overall survival in a segmented health system.

## Repository Structure

The analysis is organized into modular Jupyter Notebooks (using the R kernel) corresponding to the manuscript's tables and figures:

### 1. Epidemiological Trends

* 
**`Figure 1-2 - Trends in Annual Lymphoma Case.ipynb`**: Documents the 166% increase in absolute case volume and sex-stratified trends over time .



### 2. Descriptive & Quality Analysis

* 
**`Table 1 - Baseline Characteristics.ipynb`**: Generates sociodemographic and clinical summaries for the  cohort .


* 
**`Table 2 - Quality of Diagnosis.ipynb`**: Analyzes diagnostic methods (Histology vs. DCO) across institutional sectors, identifying the 202 "unconnected" patients .


* 
**`Table S2 - Tumor Multiplicity.ipynb`**: Compares single primary vs. multiple primary cases to identify survivorship bias .



### 3. Survival Analysis & Multivariable Modeling

* 
**`Figure 3 Table S3 - Cox Proportional Hazards Model.ipynb`**: Reproduces the multivariable Cox model showing the 28% excess mortality risk for MSP (aHR 1.28) and the education-mortality gradient (aHR 2.07) .


* 
**`Figure 4 - OS Stratified by Sector & Education.ipynb`**: Kaplan-Meier survival curves demonstrating disparities by institutional entry point and socioeconomic status .



### 4. Sensitivity & Geographic Analysis

* 
**`Figure S1 - Survival by Tumor Site.ipynb`**: Kaplan-Meier analysis of gastric vs. nodal presentations .


* 
**`Figure S2 - Survival by Socioeconomic Zone.ipynb`**: Parish-level geographic analysis confirming that institutional affiliation outweighs neighborhood as a survival predictor .



## Requirements

* 
**Language**: R (version 4.4.3).


* 
**Key Packages**: `tidyverse`, `survival`, `survminer`, `gtsummary`, `lubridate`.



## Ethical Considerations

This research was approved by the **CEISH of SOLCA Núcleo Quito (Protocol: 031-2025)**. All data used in these scripts are de-identified to comply with national data protection regulations .

### Data Dictionary: Variable Mapping and Definitions

The following table maps raw variables from the National Tumor Registry (RNT) to the derived variables used in the analysis:

| Raw Variable Name | Derived Variable | Description / Categories |
| :--- | :--- | :--- |
| `Anio_diag` | **Year of Diagnosis** | Year of first lymphoma diagnosis (1996–2019). |
| `Anio_nac` | **Age** | Age calculated at diagnosis. Dataset filtered for adults >= 18. |
| `Sexo` | **Sex** | Factorized into "Female" and "Male". |
| `Nivel_educ` | **Education Level** | Grouped into: None/Illiterate, Primary, Secondary, and Higher. |
| `Establecimiento` | **Sector / Entry Point** | MSP (Public), IESS (Social Security), SOLCA, and Private. |
| `Morf_tumor_CIEO3` | **Histological Subtype** | Coded by ICD-O-3: DLBCL, Follicular, Hodgkin, T/NK-Cell, Burkitt, and NOS. |
| `Localiz_tumor_r` | **Tumor Site** | Categorized as Nodal, Gastric (Extranodal), and Other Extranodal. |
| `Parr_res` | **Residence Area** | Urban (Quito core) vs. Rural (surrounding parishes). |
| `Num_tumores` | **Tumor Multiplicity** | Defines "Survivors" as those with >= 2 primary tumors. |
| `Metodo_diag` | **Basis of Diagnosis** | Identifies DCO (Death Certificate Only) vs. Morphological confirmation. |
| `Status_vital` | **Outcome (OS)** | Survival status linked via Civil Registry and hospital records. |
