# Ames Housing Price Prediction | Machine Learning

**Academic group project — IT3091 Machine Learning (2026)**

## Overview
A machine-learning valuation prototype trained on historical **Ames, Iowa** housing records. The primary objective is to estimate residential sale price; a secondary objective is to inspect associations between property attributes and price. **This is not trained on Sri Lankan real-estate transactions.**

## Dataset
- Kaggle — **House Prices: Advanced Regression Techniques** (Ames Housing).
- 1,460 labelled houses in the competition training file; internal random split: **1,168 training / 292 holdout**.
- The Kaggle unlabelled competition test data is distinct from the 292-row internal holdout.
- Raw Kaggle files are downloaded by the notebook after the user accepts the competition rules and configures Kaggle access.

## Machine-learning workflow
- Data dictionary inspection, missingness checks, structural absence handling and EDA.
- Numerical preprocessing: **RobustScaler + 5-neighbour KNN imputation**.
- Categorical preprocessing: mode imputation, rare-category grouping and one-hot encoding.
- Five-fold CV and hyperparameter comparison of **Linear Regression, Ridge Regression, Random Forest and Gradient Boosting**, plus a constant-price baseline.
- Both raw and `log1p` target approaches are compared. Model-selection criteria prioritize validation RMSE in dollars.
- Holdout evaluation using MAE, RMSE and R², plus residual and large-error inspection.
- **Additional exploratory** comparisons of engineered features (TotalArea, TotalBathrooms, QualityArea) and PCA. These did not replace the earlier selected holdout-tested model.

## Reported model performance (internal holdout)
| Model | MAE (USD) | RMSE (USD) | R² |
|---|---:|---:|---:|
| Selected regularized Gradient Boosting, log target | 15,745.49 | 28,018.87 | 0.8977 |
| Mean-price baseline | 62,575.93 | 87,619.04 | approximately -0.001 |

The selected model reduces RMSE **68.02% compared with the baseline** on this internal holdout. Results are historical and are not a guarantee of pricing accuracy. A later engineered-feature experiment produced **CV RMSE ≈ USD 24,536.55** but has **no new independent holdout score**.

## Technologies
Python, pandas, NumPy, scikit-learn, Matplotlib, seaborn, Jupyter/Google Colab, Kaggle client.

## Running the notebook
1. Download the dataset from the official Kaggle House Prices competition (accept competition rules).
2. Use a Python notebook environment with the libraries used in the notebook.
3. Supply Kaggle credentials securely when prompted — **never commit `kaggle.json`, API keys, tokens or credential output to GitHub**.
4. Run the notebook in order. Historical notebooks may contain Colab-specific paths such as `/content/results`.

## Which notebook to publish?
Use the **extended** notebook supplied separately as `ML_House_Price_Feature_Engineering_PCA (1) (1).ipynb` (rename it to `house_price_analysis.ipynb`). It contains the original analysis plus the feature-engineering/PCA experiments referenced by the report. Do not upload both the old and extended notebook as though they are separate projects.

## Limitations and contributions
The data is historical and US-specific, and the internal holdout may be optimistic because of earlier exploration and reuse of CV folds. The project is a **group academic prototype**, not a deployed price app. Review saved notebook outputs for visible account identifiers before publication. Properly credit Kaggle, dataset authors, libraries and teammates.

**My contribution:** _[Specify only tasks you personally completed.]_

**Demo:** https://youtu.be/TuuvvUxOXbQ (verify visibility and permission before sharing).
