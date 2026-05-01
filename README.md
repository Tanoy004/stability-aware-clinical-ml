# Stability-Aware Multi-Objective Clinical Prediction

## Overview

This repository presents a **stability-aware multi-objective evolutionary optimization framework** for robust and trustworthy clinical prediction across heterogeneous healthcare datasets.

The project was developed as part of a **Computational Intelligence course final submission**, and is currently being extended toward **journal publication**.

Unlike traditional approaches that focus only on predictive accuracy, this framework jointly optimizes:

* Predictive performance
* Explanation stability
* Feature compactness
* Model robustness

---

## Problem Motivation

Clinical machine learning models are often evaluated based on accuracy or AUC alone. However, in real-world healthcare systems, models must also be:

* Interpretable for clinical decision-making
* Stable under retraining
* Robust to data variability
* Efficient with fewer features

This project addresses these limitations using a **multi-objective optimization strategy**.

---

## Methodology

The proposed framework integrates the following components:

### 1. Leakage-Safe Preprocessing

* Median / mode imputation
* Missingness indicators
* Dataset-specific corrections
* Encoding (One-hot / WOE)
* Imbalance handling (SMOTE / class weights)

### 2. Baseline Models

* Logistic Regression
* Random Forest
* XGBoost
* LightGBM

### 3. Ensemble Learning

* Bagging
* Soft Voting
* Stacking

### 4. Explainability (SHAP)

* Feature importance using SHAP
* Bootstrap-based stability estimation
* Jaccard similarity for explanation consistency

### 5. Multi-Objective Optimization (NSGA-II)

Optimizes:

* AUPRC (performance)
* SHAP stability
* Feature count
* Validation variance

### 6. Model Selection

* Pareto front analysis
* Knee-point selection for balanced solution

---

## Datasets

The framework is evaluated on three benchmark datasets:

* **Heart Disease (UCI)**
* **Pima Indians Diabetes**
* **Chronic Kidney Disease (CKD)**

These datasets differ in size, imbalance, and feature complexity, enabling robust evaluation.

---

## Experimental Setup

* Repeated Stratified Cross-Validation
* Leakage-safe pipeline (no data leakage)
* Metrics:

  * AUROC
  * AUPRC (primary metric)
  * Balanced Accuracy
  * SHAP Stability
  * Feature Count

---

## Key Results

* **XGBoost** performed best as a baseline model
* **Ensemble methods** improved predictive performance
* **NSGA-II** selected compact and stable feature subsets
* Trade-offs observed between accuracy and interpretability

---

## Installation

Clone the repository:

```
git clone https://github.com/your-username/stability-aware-clinical-ml.git
cd stability-aware-clinical-ml
```

Install dependencies:

```
pip install -r requirements.txt
```

---

## Usage

Run the notebook:

```
Final_version.ipynb
```

The notebook includes:

* Data preprocessing
* Model training
* Evaluation
* SHAP analysis
* NSGA-II optimization
* Result visualization

---

## Reproducibility

This repository is designed to be fully reproducible:

* Fixed random seeds
* Leakage-safe validation
* Modular pipeline
* Consistent evaluation metrics

---

## Code Availability

The complete implementation, datasets (links), figures, and results are available in this repository.

This GitHub repository is used for:

* Course project submission
* Reproducibility support
* Journal manuscript reference
---

## Author

**Tanoy Debnath**
PhD Student, School of Computing
Georgia Southern University

---

## Acknowledgment

This work is part of the Computational Intelligence coursework and aims to contribute toward **trustworthy and explainable AI in healthcare systems**.
