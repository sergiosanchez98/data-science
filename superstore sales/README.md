# Superstore Sales Analysis

This project analyzes sales and profitability data from a fictional **Superstore** to identify key business drivers and areas of improvement.  
The main objective was to explore sales performance, understand profit behavior across product categories and customer segments, and detect factors that negatively impact overall profitability.

The analysis was carried out entirely in **Python** using `pandas`, `seaborn`, and `matplotlib`, following a business-oriented data exploration workflow.

---

## Key Insights

1. **Overall Performance**
   - The dataset covers several years of sales transactions across four U.S. regions.
   - Despite healthy overall sales growth, profitability is inconsistent among product categories.

2. **Category Analysis**
   - **Technology** and **Office Supplies** maintain solid profit margins (~17%), showing efficient pricing and discount policies.
   - **Furniture**, however, shows extremely low profitability (around 2–3%) and, in many cases, losses.

3. **Root Cause**
   - Within the *Furniture* category, sub-categories such as **Tables** and **Bookcases** present *negative profit values*, mainly due to **excessive discounts** (average discount above 25%).
   - These findings suggest that pricing strategy rather than regional performance is the main driver of losses.

4. **Customer Segments**
   - The *Corporate* and *Home Office* segments perform better than *Consumer* in terms of margin, possibly due to more stable purchasing patterns and less aggressive discounts.

---

## Visual Analysis
Exploratory Data Analysis (EDA) included:
- Total **Sales**, **Profit**, and **Profit Margin** evolution by year.
- Category and sub-category level performance visualized through bar and line plots.
- Combined visual showing **Profit** (bars) and **Average Discount** (dashed line) for each sub-category of *Furniture*, highlighting the direct relationship between high discounts and negative margins.

All visualizations were created using a consistent design language (white grid background, soft green palette, and clear annotation) to ensure professional readability.

---

## Tools and Technologies
- **Python**: data analysis and visualization  
- **Pandas**: data manipulation  
- **Matplotlib / Seaborn**: business-style plotting  
- **VSCode + Jupyter Notebooks**: interactive workflow  
- **GitHub**: portfolio publication and version control

---

## Business Impact
The project demonstrates the ability to:
- Translate raw sales data into actionable insights.
- Identify unprofitable product lines through quantitative analysis.
- Communicate findings visually and clearly for non-technical stakeholders.

This analysis concludes that **revising discount policies and pricing strategy for the Furniture category** could significantly improve total profit without increasing sales volume.

---

## Repository Structure
superstore sales/
│── data/
│ └── superstore.csv
│── notebooks/
│ └── superstore.ipynb           
│── README.md                         

---

Author : Sergio Sánchez