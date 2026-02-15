# Early Detection of Parkinson’s Disease Using Digital Biomarkers

## Overview

This project implements a machine learning framework for early-stage Parkinson’s Disease (PD) detection using digital biomarkers. The objective is to identify subtle, non-invasive indicators of Parkinson’s Disease suitable for early screening, rather than relying on traditional clinical motor scores.

The system is designed to be compatible with the Parkinson’s Progression Markers Initiative (PPMI) dataset.

---

## Research Objective

- Develop a machine learning model to distinguish Early-Stage Parkinson’s Disease (PD) from Healthy Controls (HC).
- Focus on baseline (initial visit) data to simulate real-world screening scenarios.
- Prioritize digital biomarkers over diagnostic motor scales.
- Ensure interpretability using SHAP-based analysis.

---

## Dataset

Current development uses a high-fidelity synthetic dataset simulating:

- 200 subjects
- Binary classification: Early PD vs Healthy Control
- Features:
  - Voice Jitter (%)
  - Gait Speed (m/s)
  - Age
  - Sex

The synthetic dataset mimics realistic PPMI distributions. The pipeline is structured to allow direct integration of official PPMI CSV files once access is approved.

---

## Methodology

### Cohort Definition
- Baseline visits only
- Binary classification: Early PD vs HC

### Feature Engineering
Digital biomarkers modeled to reflect clinically realistic trends:
- Increased voice instability in PD
- Reduced gait speed in PD
- Overlapping distributions to simulate realistic classification difficulty

---

## Modeling Approach

Two models were implemented using a champion–challenger framework:

### Logistic Regression
- Baseline linear model
- Approximate accuracy: 80%
- Demonstrates linear separability of digital biomarkers

### XGBoost Classifier
- Non-linear gradient boosting model
- Approximate accuracy: 70%
- Provides more realistic generalization for early-stage detection

---

## Evaluation

Evaluation metrics:
- Accuracy
- Confusion Matrix
- Feature Importance
- SHAP Analysis

Validation strategy prioritizes generalization to unseen subjects.

---

## Explainability

SHAP (SHapley Additive exPlanations) was used to interpret model predictions.

Findings:
- Gait Speed identified as the strongest predictor
- Voice Jitter identified as the second strongest predictor
- Demographic features show limited influence

This confirms that the model primarily learns disease-relevant digital biomarkers.

---

## Current Status

- End-to-end pipeline implemented:
  - Data loading
  - Preprocessing
  - Model training
  - Evaluation
  - Interpretability analysis
- Ready for integration with official PPMI data
- Structured for extension to longitudinal progression analysis

---

## Future Work

- Integration of real PPMI dataset
- Longitudinal modeling of disease progression
- Multimodal biomarker fusion
- Comparative evaluation with recent 2025–2026 deep learning approaches

---

## Technology Stack

- Python
- Pandas
- Scikit-learn
- XGBoost
- SHAP
- Matplotlib
