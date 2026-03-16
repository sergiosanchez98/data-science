# Telco Customer Churn Analysis

## Project Overview
This project focuses on analyzing customer churn behavior for a telecommunications company.  
The objective was to identify the key drivers behind customer attrition and to build predictive models capable of estimating the likelihood of a customer leaving.  
The analysis integrates **data exploration, statistical analysis, machine learning models, and a Power BI dashboard** that highlights actionable business insights.

---

## Dataset
The dataset `Telco-Customer-Churn.csv` contains **7,043 customer records** and **21 features**, including demographic information, service usage patterns, and billing details.  
The target variable is **`Churn`**, which indicates whether a customer has left (`Yes`) or stayed (`No`).

Key columns include:
- `gender`, `SeniorCitizen`, `Partner`, `Dependents` — customer demographics  
- `tenure`, `InternetService`, `Contract`, `PaymentMethod` — service and contract details  
- `MonthlyCharges`, `TotalCharges` — billing metrics  
- `Churn` — churn indicator (target variable)

---

## Data Analysis and Insights
A full exploratory data analysis (EDA) was performed using **Python (pandas, seaborn, matplotlib)**.

Main findings:
- The **churn rate was 26.5%**, meaning roughly one in four customers left.  
- Customers with **month-to-month contracts** showed a significantly higher churn rate compared to those with annual or two-year contracts.  
- Clients paying through **electronic check** had a much higher probability of leaving, indicating possible issues with perceived payment convenience.  
- **Senior citizens** and customers with **fiber optic services** also had a higher churn tendency.  
- Longer-tenure customers tend to remain loyal, with the churn rate dropping sharply after the first 12 months.

---

## Machine Learning Models

The predictive modeling phase focused on supervised learning techniques to classify churn:

1. **Random Forest Classifier**
   - Baseline accuracy: ~73%
   - ROC-AUC: ~0.80  
   - Good performance but biased toward the majority class (non-churners).

2. **Tuned Random Forest**
   - Improved accuracy: ~78%
   - Better recall for churned customers (around 50%)
   - Feature importance analysis showed `tenure`, `MonthlyCharges`, and `Contract` as dominant predictors.

3. **Gradient Boosting Classifier**
   - Best overall model with:
     - **Accuracy:** 79.8%
     - **ROC-AUC:** 0.84  
   - Improved ability to identify customers likely to churn.

Key features impacting churn:
- **Tenure (negative correlation)** — the longer the customer stays, the lower the probability of churn.  
- **Contract type** — long-term contracts strongly reduce churn probability.  
- **MonthlyCharges and InternetService** — high monthly fees and fiber-optic plans increase churn risk.  

---

## Power BI Dashboard

A **Power BI executive and analytical dashboard** was built to visualize business insights interactively.  
It includes:
- **KPIs:** Total Customers, Churn Rate, Avg. Monthly Charges, Avg. Tenure.  
- **Analytical Visuals:**  
  - Churn rate by Contract Type, Internet Service, and Payment Method.  
  - Average Tenure and Charges by Churn Status.  
  - Customer segmentation filters (Contract, Gender, Payment Method, Internet Service).  

### Key Business Insights:
- Customers on **month-to-month contracts** and **electronic check payments** are the most likely to churn.  
- High-churn clusters were identified among **short-tenure customers** and **fiber optic users**.  
- Extending contract duration or offering payment incentives could significantly reduce churn.  

---

## Technologies Used
- **Python:** pandas, numpy, seaborn, matplotlib, scikit-learn  
- **Power BI:** Dashboard design, DAX measures, and KPI visualizations  
- **Git & GitHub:** Version control and project documentation  

---

## Conclusions
This project demonstrates a complete **end-to-end data science workflow**, from raw data to business-ready insights.  
Through EDA, machine learning, and dashboarding, we identified actionable patterns that can guide retention strategies.  

The **Gradient Boosting model** achieved solid predictive power, and the **Power BI dashboard** provides management with a clear view of where churn risk is concentrated.

---

## Repository Structure
telco customer churn/
│── dashboards/
│ └── Telco Churn.pbix
│── data/
│ └── telco_churn_clean_powerbi.csv
│ └── Telco-Customer-Churn.csv
│── notebooks/
│ └── churn.ipynb           
│── README.md                         

---

Author : Sergio Sánchez
