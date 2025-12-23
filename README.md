# What Drives the Price of a Used Car?

## Overview
This project analyzes a large used car dataset from Kaggle (426,000+ vehicles) to identify the key factors that influence vehicle pricing. The goal is to provide actionable, data-driven recommendations to used car dealerships to help fine-tune inventory selection and pricing strategies.

The analysis follows the **CRISP-DM framework**, moving from business understanding through data preparation, modeling, evaluation, and recommendations.

---

## Business Problem
Used car dealers must decide which vehicles to stock and how to price them competitively. Understanding which vehicle attributes most strongly influence price allows dealers to:
- Prioritize high-value inventory
- Avoid overpaying for low-value features
- Improve pricing accuracy and profitability

---

## Data
- Source: Kaggle Used Vehicles Dataset  
- Size: ~426,000 rows (sampled from original 3M+ dataset)
- Key fields include:
  - Price
  - Year / vehicle age
  - Odometer
  - Manufacturer & model
  - Condition
  - Fuel type, transmission, drive type
  - Title status and location (state)

---

## Approach (CRISP-DM)
1. **Business Understanding**  
   Defined the problem as a supervised regression task to model vehicle price as a function of vehicle attributes.

2. **Data Understanding & Preparation**  
   - Removed duplicates and invalid records  
   - Filtered unrealistic prices and years  
   - Engineered vehicle age  
   - Handled missing values  
   - Encoded categorical variables using one-hot encoding  
   - Applied log transformation to price for improved model stability  

3. **Modeling**
   Multiple regression models were evaluated:
   - Baseline (median predictor)
   - Linear Regression
   - Ridge Regression (with hyperparameter tuning)
   - Lasso Regression (with hyperparameter tuning)
   - Random Forest Regression (with hyperparameter tuning)

   Cross-validation and grid search were used to ensure robust model comparison.

4. **Evaluation**
   - **Evaluation Metric:** Root Mean Squared Error (RMSE)  
   - Rationale: RMSE penalizes large pricing errors and remains interpretable in price units.  
   - Models were compared using cross-validated RMSE.

---

## Key Findings
The most influential factors affecting used car prices are:

- **Vehicle Age:** Newer vehicles command significantly higher prices.
- **Mileage (Odometer):** Higher mileage consistently reduces price, even after controlling for age.
- **Condition:** Vehicles listed in “good” or “excellent” condition receive a clear price premium.
- **Title Status:** Clean titles are strongly associated with higher prices.
- **Manufacturer & Model:** Certain brands and models retain value far better than others.
- **Drive Type & Transmission:** AWD/4WD vehicles and automatic transmissions often sell for more, depending on region.

---

## Recommendations for Dealers
- Prioritize **newer, lower-mileage vehicles** when acquiring inventory.
- Avoid vehicles with **salvage or rebuilt titles** unless heavily discounted.
- Focus on **high-retention manufacturers and models** in your local market.
- Use **condition and mileage** as primary pricing levers.
- Be cautious about overpaying for cosmetic features that show limited price impact.

---

## Next Steps
- Incorporate regional demand trends and seasonality.
- Add trim-level and optional feature data if available.
- Explore time-based pricing models as markets fluctuate.
- Evaluate nonlinear models for further performance gains.

---

## Notebook
📓 **Full Analysis Notebook:**  
`prompt_II.ipynb`

---

## Repository Structure
```
├── README.md
├── prompt_II.ipynb
├── data/
│   └── vehicles.csv
```

---

## Tools & Libraries
- Python
- pandas, NumPy
- seaborn, matplotlib
- scikit-learn

---

This project was completed as part of **Required Assignment 11.1 – What Drives the Price of a Car?**
