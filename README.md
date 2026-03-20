# Obesity Paradox in the ICU: Mechanisms and Variation Analysis

### Project Overview

This repository contains the R script and methods needed to reproduce a causal mediation and variation analysis of the obesity 
paradox in intensive care units. The analysis investigates whether the protective effect of obesity on ICU mortality is a direct 
physiological mechanism or an indirect result of clinical interventions, specifically invasive mechanical ventilation.
It also includes a semi-synthetic data simulation for methodological validation and an E-value sensitivity analysis to assess the validity of the findings against unmeasured confounding.

### Data Access and Requirements

The data used in this project comes from the MIMIC-IV dataset, which contains restricted electronic health records from patients at the Beth 
Israel Deaconess Medical Center. Due to strict data usage agreements and HIPAA privacy regulations, the raw CSV files are not included in this 
repository. In order to reproduce this analysis, researchers must independently obtain access to MIMIC-IV. This requires completing the required human 
subjects research training course through CITI, creating an account on PhysioNet, then signing the data use agreement for the MIMIC-IV 
clinical database.

### Repo Setup

Once access is granted, download the compressed dataset files from PhysioNet. You only need to download five specific files for this 
analysis. From the hospital module, download patients.csv.gz, admissions.csv.gz, and omr.csv.gz. From the ICU module, download icustays.csv.gz 
and procedureevents.csv.gz. Place all five of these compressed files directly into the main directory of this repository alongside the R script. Do not decompress the files, as the script is designed to read them directly to save local storage space.

### Software and Packages

This analysis requires R and RStudio to run. The script relies on four specific packages for data manipulation and causal modeling. You must install the dplyr package for data wrangling, the readr package for loading the compressed datasets, the mediation package for computing the natural direct and indirect effects, and the EValue package for conducting the sensitivity analysis.

### Running Analysis

Open the analysis script in RStudio. The code is written as a single, continuous pipeline that loads the data, defines the cohort, handles missing values, and runs the generalized linear models. Execute the entire script at once. The script will output three separate mediation summaries to the console, followed by the semi-synthetic simulation results and the calculated E-value.

#### References and Licensing
Johnson, A., Bulgarelli, L., Pollard, T., Horng, S., Celi, L. A., & Mark, R. (2023). MIMIC-IV (version 2.2). PhysioNet. RRID:SCR_007345. https://doi.org/10.13026/6mm1-ek67

Johnson, A.E.W., Bulgarelli, L., Shen, L. et al. MIMIC-IV, a freely accessible electronic health record dataset. Sci Data 10, 1 (2023). https://doi.org/10.1038/s41597-022-01899-x

Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P. C., Mark, R., ... & Stanley, H. E. (2000). PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation [Online]. 101 (23), pp. e215–e220. RRID:SCR_007345.
