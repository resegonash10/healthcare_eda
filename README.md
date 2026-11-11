# Healthcare Data Quality, Auditing & Statistical Reporting Portfolio

**Author:** Letlhogonolo Resego Gasealahwe  
**Core Focus:** Health Data Capturing, Record Validation, Database Auditing & Statistical Reporting  
**Tools:** Python (Pandas, NumPy, Matplotlib, Seaborn), SQL, Microsoft Excel, Databricks  

---

## Portfolio Overview
This repository presents two practical healthcare data projects demonstrating strict attention to detail, zero-error record keeping, and management reporting. These workflows reflect the daily data integrity, reconciliation, and statistical reporting standards required for managing public health information systems such as **Tier.Net, DHIS, and HIM**.

---

## Project 1: Healthcare Admissions Data Quality Audit & Statistical Reporting
**Notebook File:** `healthcare_exploratory_data_analysis.ipynb` *(Update filename if renamed)*

### 1. Objective
To audit a raw hospital admissions dataset of **55,500 patient records** across **15 clinical and administrative fields** for completeness, accuracy, and consistency, and to produce clear statistical summaries and charts for hospital management.

### 2. Data Quality Audit & Error Resolution
Before generating statistics, a protected working copy of the raw dataset was audited to prevent double-counting or financial reporting errors:
* **Completeness Check:** Inspected all 15 columns (`Name`, `Age`, `Gender`, `Blood Type`, `Medical Condition`, `Date of Admission`, `Doctor`, `Hospital`, `Insurance Provider`, `Billing Amount`, `Room Number`, `Admission Type`, `Discharge Date`, `Medication`, `Test Results`) and confirmed **0 missing values**.
* **Duplicate Record Removal:** Detected and eliminated **534 exact duplicate admission rows**.
* **Invalid Value Removal:** Identified and removed **108 records containing negative billing amounts** (as low as -2,008.49), resulting in **54,860 verified, error-free patient records**.
* **Record Standardisation:** Standardised inconsistent mixed-case patient names (e.g., *"Bobby JacksOn"*) into uniform Title Case (*"Bobby Jackson"*) and converted text-based Admission and Discharge dates into standard calendar date formats.

### 3. Structured Reporting Fields Created
To support routine hospital tracking and monthly reconciliations, **8 new administrative reporting columns** were created from the validated records:
* **Length of Stay (`Length_of_Stay`):** Calculated exact days spent in hospital per admission.
* **Calendar Breakdowns:** Extracted `Admission_Year`, `Admission_Month`, `Admission_Month_Name`, and `Admission_Day_Name` to monitor seasonal and monthly intake trends.
* **Patient & Cost Categories:** Grouped records into structured reporting bands for **Age Group** (`Child`, `Young Adult`, `Adult`, `Senior`, `Elderly`), **Stay Category** (`Short`: ≤3 days, `Medium`: 4–7 days, `Long`: 8+ days), and **Billing Bucket** (`Low`, `Medium`, `High`, `Very High`).

### 4. Visual Insights & Management Takeaways

#### Admissions by Medical Condition
![Admissions by Medical Condition](chart1_medical_conditions.png)
* **Management Takeaway:** Patient volume is distributed across six chronic and acute conditions, led by **Arthritis (9,207 admissions)** and **Diabetes (9,197 admissions)**, followed by Hypertension (9,131), Obesity (9,127), Cancer (9,121), and Asthma (9,077).

#### Admissions by Intake Type
![Admissions by Admission Type](chart2_admission_types.png)
* **Management Takeaway:** Planned **Elective admissions (18,437)** represent the largest intake category, followed closely by **Urgent (18,353)** and **Emergency (18,070)** visits—highlighting the need for accurate pre-admission scheduling and record capturing.

#### Patient Age Profile
![Age Distribution](chart3_age_groups.png)
* **Management Takeaway:** Patient ages range from **13 to 89 years** (average age: **51.5 years**), with **Elderly patients aged 66+ (16,064 visits)** forming the largest demographic group requiring ongoing chronic-care tracking.

#### Yearly Admission Trends (2019–2024)
![Yearly Admission Trends](chart4_yearly_trends.png)
* **Management Takeaway:** Annual patient intake remained consistently high between 2020 and 2023 (**over 10,790 admissions per year**), with peak monthly intake occurring in **August (4,777)** and **July (4,762)**.

#### Average Billing & Hospital Stay Duration
![Average Billing by Condition](chart5_average_billing.png)
* **Management Takeaway:** Average treatment billing remains consistent across conditions (between **25,205.92** and **25,859.22**), while **Asthma patients** recorded the longest average hospital stay (**15.68 days**), indicating an area for targeted discharge planning.

---

## Project 2: Patient Readmission & Clinical Indicator Case Study
**Notebook File:** `patient_readmission_analysis.ipynb` *(Update filename if renamed)*

### 1. Objective
To clean, validate, and analyse historical hospital visit records to identify clinical and administrative factors linked to **patient readmissions within 30 days of discharge**.

### 2. Data Validation & Preprocessing Actions
* **Clinical Record Cleaning:** Audited patient demographics, admission types, length of stay, diagnosis counts, blood pressure, blood sugar levels, and prior admission history to resolve missing values and standardise categorical fields.
* **Risk & Pattern Analysis:** Conducted statistical comparisons to examine how prior hospital visits and multiple diagnoses impact 30-day readmission rates.

### 3. Visual Insights & Management Takeaways

#### 30-Day Readmission Rate by Admission Type
![Readmission by Admission Type](readmission_by_type.png)
* **Management Takeaway:** Comparing readmission percentages across admission types enables clinic administrators to flag high-risk discharge categories for timely patient follow-up.

#### 30-Day Readmission Rate by Number of Diagnoses
![Readmission by Diagnoses](readmission_by_diagnoses.png)
* **Management Takeaway:** Patients with higher numbers of recorded diagnoses show increased readmission likelihood, demonstrating why complete and accurate diagnosis capturing at discharge is critical for patient care continuity.

---

## Summary of Administrative & Data Competencies
* **Zero-Error Data Capturing & Auditing:** Duplicate detection, missing-value verification, anomaly removal, and date standardisation.
* **Monthly Data Reconciliation:** Row-count verification, cross-tabulation checks, and categorical grouping.
* **Executive & Statistical Reporting:** Translating raw clinical records into plain-language summaries and clear visual charts for healthcare decision-makers.
