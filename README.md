# Real-World Evidence Study Using MIMIC-IV 
## Predictors of 30-Day Hospital Readmission

---

## Project Overview
This project is a **retrospective real-world evidence (RWE) study** conducted using the **MIMIC-IV clinical database**, a large, publicly available, de-identified electronic health record (EHR) dataset. 

The objective is to evaluate **clinical and demographic predictors of 30-day hospital readmission** among adult inpatient populations. Hospital readmission is a widely used quality metric with implications for patient outcomes, healthcare utilization, and cost.

---

## Study Objective
To identify demographic, clinical, and admission-related factors associated with **30-day hospital readmission** using de-identified EHR data from adult patients admitted to a tertiary academic medical center.

---

## Data Source
- **Database:** MIMIC-IV (Medical Information Mart for Intensive Care IV)
- **Institution:** Beth Israel Deaconess Medical Center
- **Data Type:** De-identified electronic health record data
- **Access:** Credentialed access via PhysioNet

---

## Data Handling and Storage

No intermediate or processed data files are stored in this repository. All cohort construction and data preprocessing were performed upstream using SQL in PostgreSQL. Analysis‑ready tables were queried directly into pandas for exploratory analysis and modeling. This approach ensures a single source of truth, avoids data duplication, and mirrors common real‑world clinical analytics workflows.

---

## Study Design
- **Design:** Retrospective observational cohort study 
- **Methodology:** Secondary analysis of real-world clinical data 
- **Outcome Type:** Binary outcome (readmitted within 30 days: Yes/No)

---

## Cohort Definition

### Inclusion Criteria
- Adult patients aged ≥ 18 years
- At least one completed inpatient hospital admission
- Valid admission and discharge dates

### Exclusion Criteria
- In-hospital mortality during the index admission
- Missing discharge information

### Index Admission
The **index admission** is defined as the first qualifying inpatient hospitalization for each patient during the study period.

---

## Outcome Definition

### Primary Outcome
**30-day hospital readmission**, defined as any inpatient hospital admission occurring within 30 days of discharge from the index admission.

---

## Predictor Variables

### Demographics
- Age
- Sex

### Admission Characteristics
- Admission type (emergency, elective, urgent)
- Length of stay (LOS)

### Clinical Factors
- Comorbidity burden derived from ICD diagnosis codes
- Selected chronic conditions (e.g., diabetes, heart failure, renal disease)

---

## Key MIMIC-IV Tables Used
- `patients`
- `admissions`
- `diagnoses_icd`

---

## Tools & Technologies
- **Database:** PostgreSQL 
- **Programming Language:** Python 
- **Environment:** Conda (Miniforge) 
- **Libraries:** pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn 
- **Analysis:** SQL-based cohort construction and Python-based statistical modeling 

---

## Analysis Plan
1. Construct analysis-ready cohort using SQL
2. Perform descriptive statistics and exploratory data analysis (EDA)
3. Compute overall and subgroup-specific readmission rates
4. Fit multivariable logistic regression models to identify predictors of readmission
5. Interpret findings in a real-world clinical context

# Key Findings

 1. Overall 30‑day readmission rate was approximately 6–7%
 2. Length of stay showed a strong, positive association with readmission risk
 3. Age demonstrated a non‑linear relationship with readmission:
     Middle‑aged and older adults had lower adjusted odds than younger adults
     Risk in the oldest patients was largely mediated by hospitalization characteristics
 4. Gender was statistically associated with readmission but with a small effect size
 5. Overall model discrimination was modest (ROC‑AUC ≈ 0.56), consistent with prior literature

---

# Limitations

    Retrospective observational design
    Limited to demographic and utilization variables
    Comorbidities, prior utilization, discharge disposition, and social factors were not included
    No causal inference is implied

---

## Ethics & Data Privacy
- All data are **fully de-identified** under HIPAA Safe Harbor standards
- No attempt was made to re-identify individuals
- Use complies with PhysioNet data use agreement

---

## Skills Demonstrated
- Real-world evidence study design
- EHR data extraction and cohort definition
- Outcome modeling and risk factor analysis
- SQL for healthcare data
- Python-based statistical analysis
- Clinical interpretation of observational data

---

## Disclaimer
This project is for **educational and research purposes only**. 
Findings do not represent clinical recommendations or institutional policy.

---

## Author
**Vijeta Singh** 
PhD | Clinical & Real-World Data Analytics 
GitHub portfolio project for Clinical Data Analyst roles

---