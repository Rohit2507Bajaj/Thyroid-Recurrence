# Thyroid Recurrence Prediction Using Automata-Enhanced Machine Learning

This repository contains the implementation of a thyroid cancer recurrence prediction framework using clinical data, automata-enhanced feature engineering, and ensemble machine learning. The workflow compares two experimental settings: the original clinical dataset and an automata-enhanced dataset generated using Pushdown Automata (PDA) and Turing Machine (TM)-based feature construction.

## Repository Structure

```text
.
├── Dataset/
│   ├── Step_1_Original_Dataset.xls
│   ├── Step_2_After_PDA_8_Features.xls
│   ├── Step_3_After_TM_5_Features.xls
│   ├── Step_4_Final_Automata_Enhanced_Dataset.xls
│   └── readme.md
├── Ensemble.ipynb
├── thyroid code.ipynb
└── readme.md
```

## Project Overview

The study aims to improve thyroid recurrence prediction by transforming static clinical records into a more structured representation. The original dataset is first processed using PDA-based feature generation, which creates eight hierarchical and clinical-state features. The PDA-updated dataset is then processed using TM-based feature generation, which creates five additional transition and state-based features. The final automata-enhanced dataset is used to evaluate whether structured feature representation improves recurrence prediction.

## Experimental Scenarios

### Scenario I: Original Clinical Dataset

This scenario uses the original thyroid recurrence dataset without automata-derived features. Machine learning models are trained directly on the original clinical variables to establish the baseline predictive performance.

### Scenario II: Automata-Enhanced Dataset

This scenario uses the final dataset obtained after PDA and TM feature engineering. The added automata-derived features represent clinical hierarchy, state transitions, recurrence progression indicators, and structured disease-state information.

## Notebooks

### `thyroid code.ipynb`

This notebook performs the feature-engineering workflow. It loads the original thyroid dataset, applies PDA-based feature construction, applies TM-based feature construction, and saves each intermediate dataset step.

### `Ensemble.ipynb`

This notebook trains and evaluates machine learning models for both scenarios. It includes baseline modelling, SMOTE-based class balancing, Gini-index-based feature selection, and the proposed HASE ensemble model based on K* and LightGBM.

## Models Used

The following models are used for comparative evaluation:

- Logistic Regression (LR)
- Decision Tree (DT)
- K* instance-based classifier
- Support Vector Machine (SVM)
- Artificial Neural Network (ANN)
- Random Forest (RF)
- XGBoost (XGB)
- LightGBM (LGBM)
- HASE ensemble model using K* and LGBM

## Evaluation Metrics

The models are evaluated using the following performance metrics:

- Accuracy
- Precision
- Recall
- F1-score
- AUC
- Matthews Correlation Coefficient (MCC)
- Cohen’s Kappa

## Workflow Summary

```text
Original Dataset
      ↓
PDA Feature Engineering
      ↓
Dataset with 8 PDA Features
      ↓
TM Feature Engineering
      ↓
Final Automata-Enhanced Dataset
      ↓
Scenario-wise Model Training
      ↓
SMOTE Balancing + Gini Feature Selection
      ↓
HASE Ensemble Prediction
      ↓
Performance Evaluation
```

## Notes

- The dataset folder contains each intermediate dataset generated during the feature-engineering process.
- The notebooks should be executed in sequence: first `thyroid code.ipynb`, then `Ensemble.ipynb`.
- The final automata-enhanced dataset is used for the second experimental scenario.
- The HASE model combines instance-based and boosting-based learning to improve thyroid recurrence prediction.

## Requirements

Recommended Python packages:

```text
pandas
numpy
scikit-learn
imbalanced-learn
xgboost
lightgbm
openpyxl
matplotlib
seaborn
```

Install them using:

```bash
pip install pandas numpy scikit-learn imbalanced-learn xgboost lightgbm openpyxl matplotlib seaborn
```


