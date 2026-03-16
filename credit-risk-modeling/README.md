# Credit Risk Modeling — Probability of Default (PD)

## Project Overview

Credit risk modeling is one of the most important applications of data science in the financial industry. Financial institutions must evaluate whether loan applicants are likely to repay their debts or default on them. Incorrect decisions may lead either to financial losses or to rejecting profitable customers.

This project develops a **Probability of Default (PD) model** using machine learning techniques to identify high-risk borrowers. The workflow follows a realistic credit risk modeling pipeline including data exploration, preprocessing, model development, evaluation, explainability, and deployment preparation.

The objective is not only to achieve strong predictive performance but also to ensure that the model is **interpretable, reproducible, and aligned with business risk strategies**.

The final solution compares multiple models and selects the most appropriate one for deployment based on predictive performance and operational considerations.

---

## Business Problem

Financial institutions need to estimate the **likelihood that a borrower will default on a loan**. This probability allows lenders to:

- Approve or reject loan applications
- Adjust interest rates based on risk
- Detect high-risk customers early
- Optimize portfolio risk exposure

The goal of this project is to build a predictive model that estimates the **Probability of Default (PD)** for each applicant using demographic, financial, and behavioral variables.

Success criteria include:

- Achieving strong discriminatory power (ROC-AUC above 0.80)
- Maintaining strong recall for the default class
- Preserving interpretability and auditability
- Enabling practical use in risk decision systems

---

## Dataset

The dataset used in this project is a **tabular credit risk dataset** containing borrower information such as:

- Demographic attributes
- Financial characteristics
- Credit history indicators
- Behavioral variables

The target variable is:

**`default`**

- `1` → borrower defaulted  
- `0` → borrower did not default

Credit risk datasets are typically **imbalanced**, with significantly fewer default cases than non-default cases. This characteristic requires careful handling during modeling and evaluation.

---

## Project Workflow

The project follows a structured data science pipeline typical of credit risk modeling projects.

### 1. Data Exploration (EDA)

Exploratory analysis was conducted to understand:

- Distribution of the target variable
- Numerical feature distributions
- Categorical variable behavior
- Correlations between features
- Potential predictors of default

EDA also provided early insights into risk patterns and helped guide feature preprocessing.

---

### 2. Data Cleaning and Preprocessing

The dataset required several preprocessing steps before modeling:

- Handling missing values
- Cleaning inconsistent categorical values
- Converting numeric fields stored as strings
- Treating potential outliers
- Validating cleaned data

A preprocessing pipeline was implemented using **scikit-learn's ColumnTransformer** to handle:

**Numerical features**
- Median imputation
- Standard scaling

**Categorical features**
- Most frequent imputation
- One-hot encoding

This ensures consistent transformations during training and future scoring.

---

### 3. Train / Validation / Test Split

The dataset was split into:

- Training set
- Validation set
- Test set

This approach allows reliable model evaluation and reduces the risk of overfitting.

---

### 4. Baseline Model — Logistic Regression

Logistic Regression was implemented as a **baseline model** due to its strong interpretability and common use in credit scoring.

Advantages:

- Transparent decision logic
- Easy interpretation of feature effects
- Regulatory familiarity

While logistic regression performed well, its linear structure limits its ability to capture complex feature interactions.

---

### 5. Gradient Boosted Tree Models

Two advanced machine learning models were implemented to capture nonlinear relationships in the data.

#### LightGBM

LightGBM is an efficient gradient boosting algorithm optimized for large tabular datasets.

Key advantages:

- Strong predictive performance
- Fast training
- Effective handling of complex feature interactions

#### XGBoost

XGBoost is another powerful gradient boosting implementation widely used in risk modeling.

Advantages include:

- High predictive accuracy
- Robust regularization
- Extensive control over model complexity

Both models were trained using **class imbalance adjustments** to better capture default cases.

---

### 6. Handling Class Imbalance

Credit default datasets are inherently imbalanced. In this project:

- The **`scale_pos_weight` parameter** was used in boosting models
- Evaluation focused on metrics suitable for imbalanced classification

This approach helps ensure the model does not ignore the minority default class.

---

### 7. Model Evaluation

Multiple evaluation metrics were used to assess model performance:

**ROC-AUC**

Measures the model's ability to rank risky borrowers above safe ones.

**Precision-Recall AUC**

More informative when dealing with imbalanced datasets.

**Confusion Matrix Metrics**

- Precision
- Recall
- F1-score

Particular emphasis was placed on **recall for the default class**, as missing risky borrowers is typically more costly than incorrectly flagging safe ones.

---

### 8. Model Comparison

Three models were compared:

- Logistic Regression
- LightGBM
- XGBoost

Results showed that **gradient boosted models significantly outperform the linear baseline**.

Boosted trees achieved higher ROC-AUC and PR-AUC values and provided stronger detection of high-risk borrowers.

---

### 9. Explainability with SHAP

Interpretability is essential in credit risk modeling.

SHAP (SHapley Additive exPlanations) was used to:

- Identify the most influential features globally
- Understand individual predictions locally
- Ensure that model decisions align with domain knowledge

This step helps make the model **auditable and explainable**.

---

### 10. Threshold Tuning and Risk Strategy

The classification threshold was analyzed to align model predictions with business objectives.

Different thresholds can shift the balance between:

- Approving more customers
- Reducing default risk

This allows the institution to align model decisions with its **risk appetite**.

---

### 11. Model Selection

Based on the evaluation results, **LightGBM** was selected as the final model due to its:

- High predictive performance
- Computational efficiency
- Compatibility with SHAP explainability
- Robust handling of nonlinear feature interactions

Logistic regression remains a useful baseline, but boosting models provide superior predictive power.

---

### 12. Model Export

To prepare the model for deployment, the final pipeline was exported.

The exported pipeline includes:

- Preprocessing steps
- The trained LightGBM model

Artifacts saved:

```
artifacts/
    credit_risk_lgbm_pipeline_v1.0.0.joblib
    model_metadata_v1.0.0.json
```

Exporting the full pipeline guarantees that preprocessing and prediction steps remain consistent in production environments.

---

### 13. Scoring Interface

A scoring utility was implemented to simulate real-world deployment.

The scoring interface allows systems to:

1. Load the exported pipeline
2. Input applicant data
3. Automatically apply preprocessing
4. Predict the Probability of Default (PD)
5. Return a binary risk classification

Both **single-applicant scoring** and **batch scoring** are supported.

---

### 14. Monitoring and Future Improvements

Once deployed, the model should be monitored regularly to ensure stable performance.

Recommended monitoring practices include:

- Tracking ROC-AUC over time
- Monitoring predicted PD distributions
- Detecting feature distribution drift
- Comparing predicted vs realized default rates

Future improvements may include:

- Incorporating macroeconomic variables
- Performing advanced hyperparameter tuning
- Adding fairness analysis
- Implementing automated retraining pipelines

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- LightGBM
- XGBoost
- SHAP
- Matplotlib / Seaborn

---

## Repository Structure

```
credit-risk-model/
│
├── data/
|   └── data/credit_risk_dataset.csv
├── notebooks/
│   └── credit_risk.ipynb
│
├── artifacts/
│   ├── credit_risk_lgbm_pipeline_v1.0.0.joblib
│   └── model_metadata_v1.0.0.json
│
└── README.md
```

---

## Key Takeaways

This project demonstrates a complete end-to-end workflow for building a **credit risk Probability of Default model**, including:

- Data exploration and preprocessing
- Handling imbalanced datasets
- Model comparison and evaluation
- Explainability with SHAP
- Threshold tuning aligned with business strategy
- Exporting a deployable scoring pipeline

While simplified compared to full banking systems, the methodology reflects realistic credit risk modeling practices and provides a solid foundation for production-ready machine learning models.