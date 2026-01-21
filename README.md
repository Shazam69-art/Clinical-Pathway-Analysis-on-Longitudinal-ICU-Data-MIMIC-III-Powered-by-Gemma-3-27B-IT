# Clinical Pathway Analysis using Longitudinal Patient Data

A clinical decision support system that analyzes patient health trajectories over time using real-world ICU data. Powered by **Google Gemma 3 27B Instruct**.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/flask-3.0+-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

---

## Overview

Traditional electronic health records present fragmented snapshots of patient care. This system addresses that limitation by constructing comprehensive temporal timelines that reveal how a patient's condition evolves across months or years of clinical encounters.

The application merges disparate clinical data sources (diagnoses, procedures, medications, labs, notes) into a unified chronological view, then applies AI-powered analysis to identify disease progression patterns, treatment responses, and clinical risks that require physician attention.

---

## Dataset: MIMIC-III Clinical Database

**Dataset Link:** [MIMIC-III on Kaggle](https://www.kaggle.com/datasets/asjad99/mimiciii?resource=download)

### What is MIMIC-III?

MIMIC-III (Medical Information Mart for Intensive Care III) is a large, freely-available database comprising deidentified health-related data from patients who were admitted to the critical care units of the Beth Israel Deaconess Medical Center between 2001 and 2012.

### Dataset Characteristics

- **Patients:** 40,000+ ICU patients
- **Admissions:** 50,000+ hospital admissions
- **Records:** Millions of clinical observations
- **Time Span:** Over a decade of longitudinal data

### Data Components Used

| Table | Description | Records Used |
|-------|-------------|--------------|
| `PATIENTS.csv` | Patient demographics and mortality data | 100 patients |
| `ADMISSIONS.csv` | Hospital admission details and discharge information | 129 admissions |
| `DIAGNOSES_ICD.csv` | ICD-9 diagnosis codes for each admission | 1,761 diagnoses |
| `PROCEDURES_ICD.csv` | ICD-9 procedure codes | 506 procedures |
| `PRESCRIPTIONS.csv` | Medication orders with dosages and routes | 10,398 prescriptions |
| `LABEVENTS.csv` | Laboratory test results with timestamps | 76,074 lab results |
| `NOTEEVENTS.csv` | Clinical notes from physicians and nurses | Available |
| `CHARTEVENTS.csv` | Vital signs and other charted observations | 758,355 chart events |
| `D_ICD_DIAGNOSES.csv` | Dictionary mapping ICD-9 codes to descriptions | 14,567 codes |
| `D_ICD_PROCEDURES.csv` | Dictionary for procedure codes | 3,882 codes |
| `D_LABITEMS.csv` | Dictionary for laboratory measurements | 753 items |

---

## Technical Architecture

### Technology Stack

- **Backend:** Flask (Python)
- **Data Processing:** Pandas
- **AI Model:** Google Gemma 3 27B Instruct (via Hugging Face Router API)
- **Frontend:** Embedded HTML/CSS with vanilla JavaScript
- **Design:** Dark medical theme with Orbitron font and responsive UI

### System Components

1. **DataLoader**: Reads and standardizes MIMIC-III CSV files
2. **TimelineBuilder**: Merges all clinical events into chronological order
3. **FeatureEngine**: Extracts clinical features and temporal patterns
4. **LLMClient**: Interfaces with Gemma 3 27B for AI analysis
5. **AnalysisController**: Orchestrates the complete analysis pipeline

---

## AI Model & Prompting Strategy

### Model Selection: Google Gemma 3 27B Instruct

**Why Gemma 3 27B?**
- 128K context window (perfect for long patient timelines)
- Instruction-tuned for structured reasoning tasks
- Strong medical domain understanding
- Accessible via Hugging Face Router API

### Prompting Techniques

#### 1. System-Level Medical Constraints
