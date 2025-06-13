# Alzheimer’s Early-Diagnosis Capstone

This repository implements an end-to-end machine learning pipeline for the **early diagnosis of Alzheimer’s disease** using Orange and Python. We process a dataset of 2,149 patients (ages 60–90) with demographic, lifestyle, health-history, and cognitive test scores to build predictive models that flag early-stage Alzheimer’s.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Results & Evaluation](#results--evaluation)
- [Recommendations](#recommendations)
- [Data Ethics & Security](#data-ethics--security)
- [References](#references)

---

## Overview

Alzheimer’s disease is a progressive neurodegenerative disorder with growing global prevalence. Early detection can greatly improve care and quality of life. This project leverages a supervised machine learning approach to:

- Clean and preprocess raw clinical data
- Explore descriptive relationships (e.g., MMSE score distributions, lifestyle risk factors)
- Train four classifiers (Logistic Regression, Random Forest, Gradient Boosting, SVM) with stratified k-fold cross-validation and grid-search for hyperparameter tuning
- Interpret predictions using SHAP values and feature-importance analyses
- Evaluate performance via AUC, F₁ score, precision, and recall
- Propose clinical integration, communication strategies, and future extensions

## Features

- **Data Processing**: Duplicate removal, missing-value imputation, categorical encoding
- **Descriptive Analytics**: Histograms, boxplots, correlation matrices
- **Predictive Modeling**: Logistic Regression, Random Forest, XGBoost/LightGBM, SVM
- **Explainability**: SHAP summary and decision plots
- **Evaluation Metrics**: AUC, F₁ score, precision, recall

## Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/alzheimers-capstone.git
   ```
2. Navigate into the directory:
   ```bash
   cd alzheimers-capstone
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Prepare data:
   ```bash
   python data_prep.py
   ```
2. Run Orange workflows or execute training scripts:
   ```bash
   python train_models.py
   ```
3. View visualizations and interpret results in the `notebooks/` folder or via Orange GUI.

## Project Structure

```
├── data/                      # raw and cleaned datasets
├── notebooks/                 # Jupyter notebooks for EDA and modeling
├── workflows/                 # Orange workflow files
├── scripts/                   # preprocessing and training scripts
├── results/                   # model outputs and figures
├── requirements.txt           # Python dependencies
└── README.md                  # this file
```

## Results & Evaluation

Gradient Boosting achieved the highest performance (AUC ≈ 0.976, F₁ ≈ 0.964/0.934). Random Forest also performed strongly (AUC ≈ 0.973).

## Recommendations

- Integrate the Gradient Boosting model into EHR systems with risk thresholds
- Display risk scores (Low/Medium/High) tailored for clinicians and caregivers
- Extend with MRI/genetic data, NLP on clinical notes, and mobile app monitoring

## Data Ethics & Security

All patient records are anonymized and stored on encrypted servers in compliance with HIPAA/GDPR. Future data integration must include informed consent and bias monitoring.

## References

See the full list in `docs/references.md` for all cited studies and data sources.
