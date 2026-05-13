# breast-cancer-survival-ml
Machine learning project using TCGA-BRCA RNA-seq gene expression data to predict 5-year survival in breast cancer patients. Models include ridge regression, LASSO, and random forest. Performance is evaluated using AUC, with additional analysis of feature importance and model generalization.

## Overview

Gene expression data are high-dimensional (p >> n), making prediction challenging. This study evaluates multiple models and examines feature importance to understand which genes are associated with survival outcomes.

## Data

- Source: TCGA-BRCA (The Cancer Genome Atlas)
- Final dataset: 351 patients
- Features: Top 500 most variable genes (after preprocessing)
- Outcome: 5-year survival (1 = survived ≥5 years, 0 = died <5 years)

## Methods

- Ridge Regression (L2 regularization)
- LASSO (L1 regularization, feature selection)
- Random Forest (nonlinear modeling)

### Training Strategy
- 3-way split: Training (64%), Test (16%), Validation (20%)
- 5-fold cross-validation for hyperparameter tuning

## Results

- Ridge Regression performed best:
  - Test AUC: 0.633
  - Validation AUC: 0.727
- Random Forest: AUC = 0.610
- LASSO: AUC = 0.585

Overall performance is modest, highlighting the complexity of survival prediction using gene expression alone.

## Key Findings

- LASSO selected 70 genes as important predictors
- Random Forest identified key genes using permutation importance
- Two genes (GLT25D2, BMP7) were consistently identified across methods, suggesting more robust biological signals

## Files

- `analysis.Rmd` – R code and full analysis workflow  
- `report.pdf` – Final project report  
- `slides.pdf` – Presentation slides  

## Notes

This project was completed as part of a BS845 Statistical Modelling and Data Science course at Boston University, focusing on model comparison, evaluation, and interpretation in a high-dimensional biological dataset.
