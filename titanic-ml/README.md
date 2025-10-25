# Titanic — Machine Learning from Disaster

This repository contains my very first **Data Analytics & Machine Learning project**, built on the classic Kaggle competition: [Titanic - Machine Learning from Disaster](https://www.kaggle.com/c/titanic).  

The goal is to **predict passenger survival** on the Titanic using demographic and socioeconomic features such as age, gender, ticket class, and fare.  

Even though this is my **first end-to-end project**, I achieved a competitive **Kaggle public score of 0.75837**, demonstrating strong analytical thinking, solid methodology, and the ability to deliver results.

---

## Project Highlights
- **Comprehensive workflow**: Data exploration → preprocessing → modeling → evaluation → Kaggle submission.
- **Exploratory Data Analysis (EDA)**:  
  - Found clear survival patterns by sex (74% women vs. 19% men survived).  
  - Identified class as a strong predictor (63% survival in 1st class vs. 24% in 3rd).  
  - Analyzed non-linear relationships in `Fare` and missing values in `Age`, `Cabin`, `Embarked`.
- **Feature Engineering**:  
  - Imputed missing values with medians/modes.  
  - Encoded categorical variables (`Sex`, `Embarked`).  
  - Built simplified but effective feature set for modeling.
- **Models tested**:  
  - Logistic Regression (baseline, interpretable).  
  - Random Forest (capturing non-linearities, ROC-AUC 0.835).  
  - Gradient Boosting (tuned with cross-validation, best performance).  
- **Threshold optimization**: Adjusted decision threshold to improve recall for survivors and maximize F1 score.  

---

## Results
- **Validation accuracy**: ~81%  
- **ROC-AUC**: ~0.81  
- **Kaggle public leaderboard score**: **0.75837** 

This performance is close to Kaggle's official baseline models and shows that even in my first project I can **build a reliable pipeline and achieve competitive results**.

---

## Tools & Technologies
- **Python** (pandas, numpy, scikit-learn, matplotlib, seaborn)  
- **Jupyter Notebooks** for reproducible analysis  
- **Git/GitHub** for version control and project sharing  

---

## Key Takeaways
- Demonstrated the ability to handle a complete data science workflow from scratch.  
- Validated multiple ML models and understood their strengths/limitations.  
- Achieved a strong Kaggle score **on the very first project**.  

---

## Repository Structure
titanic-ml/                                                                   \
│── notebooks/                                                                \
│ └── TITANIC NOTEBOOK.ipynb               # Full EDA + modeling pipeline     \
| └── train.csv                                                               \ 
│ └── test.csv                                                                \ 
│── submissions/                                                              \
│ └── submission_gb_thr040.csv             # Final Kaggle submission          \
│── README.md                              # Project documentation            \

---

Author: Sergio Sánchez  

