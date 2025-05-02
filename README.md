# A Data-Driven Approach to Understanding and Predicting Chronic Absenteeism in K–12 Education

This project explores machine learning models to predict high absenteeism rates in U.S. school districts, using a combination of demographic, poverty, financial, and school characteristic data. Models were compared in terms of predictive power, interpretability, and handling of class imbalance.

## Team
**Project Group 14**
- Memeber 1 - Chase Clemence
- Memeber 2 - David Corcoran
- Memeber 3 - Gentry Lamb
- Memeber 4 - Adam Stein

## Repository Structure

```
├── README.md                         # Main project overview and instructions.
├── code/                             # Jupyter notebooks for each major step of the project.
    ├── data_cleaning.ipynb               # Scripts for cleaning and preparing raw data.
    ├── eda.ipynb                         # Exploratory Data Analysis: visualizations and summary stats.
    ├── feature_selection.ipynb           # Feature selection and engineering for modeling.
    ├── lda_qda.ipynb                     # LDA and QDA model training and evaluation.
    ├── logistic_regression.ipynb         # Logistic Regression model training and evaluation.
    ├── neural_network.ipynb              # Neural Network model training, hyperparameter tuning, and evaluation.
    ├── random_forest.ipynb               # Random Forest model training and feature importance analysis.
    ├── svm.ipynb                         # Support Vector Machine model training and evaluation.
    └── visualizations.ipynb              # Supplementary plots and model visualizations.
├── data/                             # Data files (linked externally, see below).
├── images/                           # Figures and plots generated during analysis and modeling.
├── poster/                           # Final academic poster summarizing the project.
└── report/                           # Final technical report and supporting files.
```

## Data

The `data/` folder contains both the original (raw) datasets and cleaned datasets used for modeling. Due to size limitations, the data files are not included directly in this repository.  
You can download all required data [**here**](https://drive.google.com/uc?export=download&id=1HdMoTEXhGsZiUtnqeF6Q-VM1WeC_f5Tk).

The `raw/` subdirectory contains the original datasets collected from public sources:
- **Chronic_Absenteeism_Demographics_2022.csv** — Absenteeism rates by student demographics (e.g., race/ethnicity).
- **Chronic_Absenteeism_Total_2022.csv** — Overall absenteeism rates by school and district.
- **Financial_Data_2022.csv** — Financial data such as per-student expenditures and funding sources.
- **Poverty_Data_2022.csv** — District-level poverty rates and economic disadvantage indicators.
- **Public_School_Characteristics_2022.csv** — School characteristics like enrollment size and urban/rural status.
- **demographic.csv** — Additional demographic information (e.g., disability status, English learners).

The `clean/` subdirectory contains datasets prepared for modeling:
- **cleaned_school_data.csv** — Merged and fully cleaned dataset with engineered features and handled missing values.
- **absenteeism_model_final.csv** — Final dataset used for binary classification (high absenteeism vs. not), with preprocessing steps like normalization and log transformations.
- **absenteeism_model_final_bss.csv** — Dataset modified for Best Subset Selection during feature selection.

## Modeling Overview

- **Random Forest**:  
  - Strong accuracy and AUC.  
  - Handled class imbalance well.  
  - Highlighted key features driving absenteeism.
- **Neural Network**:  
  - Highest predictive performance after hyperparameter tuning (learning rate, epochs, batch size).  
  - Sensitive to overfitting; required careful regularization.  
  - Confusion matrix showed good recall but room to improve precision.
- **Logistic Regression**:  
  - Good balance between performance and interpretability.  
  - Useful for understanding relationships through model coefficients.
- **SVM and LDA/QDA**:  
  - Lower performance.  
  - Struggled with class imbalance and non-linear relationships.

## Key Findings

- **AUC** was prioritized over accuracy due to dataset imbalance, offering a better measure of model performance.
- **Class imbalance** impacted all models; techniques like SMOTE or re-weighting could improve future results.
- **Feature engineering** (e.g., log transformations) improved model fit by reducing skewness in financial variables.
- **High correlation** among demographic and poverty features limited some models' ability to distinguish between predictors.
- **Main Predictors**: 
  - % Students in Poverty
  - Race Demographics
  - District Revenue

## Getting Started

1. Clone the repository.
2. Download data and upload into your local repository.
3. Navigate to `code/` and run the notebooks in order:  
   `data_cleaning.ipynb → eda.ipynb → feature_selection.ipynb → [modeling notebooks] → visualizations.ipynb`
4. Explore saved models and figures.
5. View the full findings in `report/` or the `poster/`.
