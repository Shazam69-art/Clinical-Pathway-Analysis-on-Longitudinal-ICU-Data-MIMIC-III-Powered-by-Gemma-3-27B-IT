# Clinical Pathway Analysis using Longitudinal Patient Data

A clinical decision support system powered by **Google Gemma 3 27B Instruct** that analyzes patient health trajectories using MIMIC-III ICU data.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/flask-3.0+-green.svg)

---

## Overview

Creates comprehensive temporal timelines from fragmented patient records. Merges diagnoses, procedures, medications, labs, and clinical notes into chronological views, then uses AI to identify disease progression patterns and clinical risks.

---

## Dataset

**MIMIC-III Clinical Database** - [Download on Kaggle](https://www.kaggle.com/datasets/asjad99/mimiciii?resource=download)

Deidentified health data from 40,000+ ICU patients at Beth Israel Deaconess Medical Center (2001-2012). Includes demographics, admissions, diagnoses (ICD-9), procedures, prescriptions, lab results, and clinical notes.

---

## AI Model

**Google Gemma 3 27B Instruct** via Hugging Face Router API

- 128K context window for long timelines
- Temperature 0.2 for focused clinical reasoning
- Structured prompts emphasizing evidence-based analysis
- Six-section output: Clinical Summary, Disease Progression, Treatment Response, Risk Factors, Longitudinal Insights, Action Items

---

## Features

- Chronological timeline visualization
- Statistical dashboard with event distribution
- AI-powered pattern detection and risk analysis
- Dark medical theme with typing animation
- Single-file Flask architecture

---

## Installation
```bash
pip install flask pandas requests
export HF_TOKEN=your_huggingface_token
python app.py
```

Update `BASE_DIR` in code to point to your MIMIC-III data location.

---

## Usage

Select patient → Click analyze → Review timeline and AI analysis

---

## Medical Disclaimer

For research and educational purposes only. Does not diagnose or recommend treatments. All clinical decisions require qualified healthcare professionals.

---

## License

MIT License

---

## Acknowledgments

MIMIC-III Database (PhysioNet), Google Gemma (DeepMind), Hugging Face
