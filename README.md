[Project report hnc mortality.pdf](https://github.com/user-attachments/files/21927819/Project.report.hnc.mortality.pdf)
# Machine Learning Prediction of Head and Neck Cancer Mortality

## Overview
This project uses machine learning algorithms (Random Forest and XGBoost) to predict mortality in head and neck cancer patients using SEER (Surveillance, Epidemiology, and End Results) registry data from 2010-2021. The analysis identifies key prognostic factors and establishes a framework for clinical decision support in oncology.

## Team Members
- **Bhanu Tejaswi Kota** - Statistical testing and visualizations
- **Maria Tecua** - SEER feature extraction and background research
- **Sumant Tiwari** - ML model development and hyperparameter tuning
- **Vidisha Ajay Uttamchandani** - Literature review and data preprocessing

## Dataset
- **Source**: SEER Registry via SEER*Stat
- **Period**: 2010-2021
- **Initial Records**: 209,851 patients
- **Final Records**: 198,940 (after cleaning)
- **Features**: 16 clinical and demographic variables including age, sex, tumor site, stage, grade, and treatment timing

## Methodology
1. **Data Extraction**: Retrieved HNC cases from SEER database
2. **Data Cleaning**: Handled missing values, removed duplicates, grouped rare categories using MySQL and Python
3. **Statistical Analysis**: Chi-square tests, Cramér's V correlation, and UMAP dimensionality reduction
4. **Model Development**: Trained Random Forest and XGBoost with 5-fold cross-validation
5. **Evaluation**: ROC-AUC scores, confusion matrices, and feature importance analysis

## Key Results
| Model | Test ROC-AUC | Accuracy | F1-Score (Dead) | Recall (Dead) |
|-------|-------------|----------|-----------------|---------------|
| **Random Forest** | 0.7814 | 0.70 | 0.72 | 0.78 |
| **XGBoost** | 0.7847 | 0.71 | 0.70 | 0.70 |

**Top Predictive Features**:
- Age at diagnosis (85+ years)
- Pathological grade
- Tumor stage (AJCC T/N/M)
- Treatment delay
- Tumor site

## Requirements
```
pandas
numpy
matplotlib
seaborn
scipy
scikit-learn
xgboost
umap-learn
mysql-connector-python
```

## Project Structure
```
├── data/
│   ├── 15april_cleaned.csv          # Cleaned dataset
│   └── raw_seer_data/                # Original SEER files
├── notebooks/
│   ├── data_exploration.ipynb
│   ├── statistical_analysis.ipynb
│   └── model_training.ipynb
├── results/
│   ├── roc_curves/
│   ├── confusion_matrices/
│   └── feature_importance_plots/
└── README.md
```

## Usage
1. Extract SEER data using SEER*Stat software
2. Load data into MySQL database and run cleaning queries
3. Execute preprocessing pipeline in Python
4. Train models using provided notebooks
5. Evaluate performance and visualize results

## Clinical Implications
- Enables early risk stratification for HNC patients
- Identifies high-risk individuals for targeted interventions
- Supports personalized treatment planning
- Provides foundation for clinical decision support systems

## Limitations
- Missing key clinical variables (HPV status, comorbidities)
- High dimensionality from one-hot encoding
- Limited to SEER dataset (external validation needed)
- No temporal survival analysis (binary classification only)

## Future Directions
- Implement survival analysis (Cox proportional hazards)
- Integrate with clinical decision support systems
- Include genomic and molecular data
- Validate on external datasets
- Apply SHAP for model interpretability

## References
- SEER Program: https://seer.cancer.gov
- Full project report available in repository

## License
This project uses publicly available SEER data for academic purposes.

---
**Contact**: Indiana University Indianapolis | bkota@iu.edu, mtecua@iu.edu, srtiwari@iu.edu, vuttamch@iu.edu
