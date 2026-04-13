# UCL Research Fellow (Health Geographer) Technical Test

This repository contains my submission for the **Research Fellow (Health Geographer)** technical test.

The work is provided as a single Python notebook and covers the following tasks:

1. **Data cleaning and quality control** of the synthetic electronic health record (EHR) tables  
2. **Descriptive analysis** of patients, observations, and conditions  
3. **Exploration of systolic blood pressure, diastolic blood pressure, and BMI** among patients with diagnosed hypertension  
4. **Estimation of crude and UK-adjusted prevalence of hypertension**

The analysis is written from the perspective of **health data science**, with additional attention to **spatial epidemiology** and **geo-analytics**, where relevant to the available data.

---

## Repository structure

```text
ucl-health-geographer-technical-test/
│
├─ README.md
├─ requirements.txt
│
├─ Technical_Test_Xiaorui_Yan.ipynb
│
├─ Input/
│   ├─ patients.csv
│   ├─ conditions.csv
│   ├─ observations.csv
│   ├─ encounters.csv
│   ├─ medications.csv
│   ├─ dictionary_loinc.csv
│   ├─ dictionary_snomed.csv
│   ├─ dictionary_rxnorm.csv
│   ├─ mass_county.gpkg
│   └─ uk_population_2022.csv
│
└─ Output/
    ├─ patients_clean.csv
    ├─ conditions_sanitized.csv
    ├─ observations_sanitized.csv
    └─ medications_sanitized.csv
```
---

## Data folders

### Input

The `Input/` folder contains the source files used in this technical test.

#### Source files provided in the test
Most files in this folder are the original source files provided as part of the technical test, including the synthetic EHR tables and the ontology lookup dictionaries.

These include:

- `patients`
- `conditions`
- `observations`
- `encounters`
- `medications`
- `dictionary_loinc`
- `dictionary_snomed`
- `dictionary_rxnorm`

These files were used as the raw input data for the cleaning, descriptive analysis, and hypertension-related analyses presented in the notebook.

#### Additional supporting files

- `mass_county.gpkg`  
  This is a county-level spatial file for Massachusetts. In this project, it was used as the county boundary layer for geographic visualisation and county-level summaries.  
  Only the following fields were used in the analysis:

  - `NAMEISAD`: county name  
  - `POP2022`: county population in 2022  

  Other columns in this file were not used and are therefore not described here.

- `uk_population_2022.csv`  
  This file contains the 2022 UK population by age group and sex, and was used for the adjusted prevalence analysis in Task 4.  
  The columns are:

  - `Age`: age group  
  - `Males`: number of males in the corresponding age group  
  - `Females`: number of females in the corresponding age group  
  - `All`: total population in the corresponding age group  

---

### Output

The `Output/` folder contains the cleaned datasets generated after **Task 1 (data cleaning and quality control)**.

These files include:

- `patients_clean`
- `conditions_sanitized`
- `observations_sanitized`
- `medications_sanitized`

These cleaned files retain the same columns as their corresponding source files, but include only records that passed the quality control and linkage checks applied in Task 1. They were then used as the input for the subsequent analyses in Tasks 2–4.

