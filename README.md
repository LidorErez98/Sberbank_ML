#  Moscow Housing Price Prediction — Sberbank Dataset (Course Project)

## Summary

This project was completed as part of a university machine learning course. We used the **Sberbank Russian Housing Market** dataset to predict apartment sale prices in Moscow between 2011 and 2016.  

Our model achieved a **score equivalent to the actual 5th place solution** on the private leaderboard.

---

##  We used this opportunity to:

- Clean and structure real-world tabular data
- Perform exploratory data analysis to understand pricing patterns
- Engineer features based on domain logic and spatial information
- Apply and compare machine learning models (XGBoost, Random Forest)
- Tune hyperparameters and reduce feature redundancy with PCA
- Build interpretable and reproducible analysis in notebooks

---

## Tools & Libraries

- Python  
- Jupyter Notebooks  
- Pandas, NumPy  
- Scikit-learn, XGBoost  
- Matplotlib, Seaborn  
- PCA, Bayesian Optimization

---

##  Repository Structure

/Data                  → Raw and cleaned CSV files
/Word Documents        → Report and documentation
/project               → Notebooks and model code
/text_files            → Supporting notes
cleaned_train.csv      → Cleaned training data
cleaned_test.csv       → Cleaned test data
macro.csv              → Macroeconomic indicators
train.csv / test.csv   → Original Sberbank data
README.md              → This file

---

##  Approach

### 1. Data Cleaning
- Dropped columns with excessive missing values or low correlation with price  
- Filled missing values using informed estimates (e.g. kitchen/living area ratios per region)  
- Fixed inconsistencies (e.g. unrealistic floor counts, invalid timestamps)

### 2. Exploratory Data Analysis (EDA)
- Explored price differences by property type (owner-occupied vs. investment)  
- Analyzed macro trends (e.g. 2015–2016 economic decline)  
- Visualized feature distributions and outliers

### 3. Feature Engineering
- Created new variables such as size ratios and temporal indicators  
- Encoded location data using smoothed average price per sub-area:

$$
\text{Encoded Price} = \left( \frac{n}{n + m} \right) \cdot \text{Local Avg} + \left( 1 - \frac{n}{n + m} \right) \cdot \text{Global Avg}
$$


### 4. Modeling
- Built separate models for each product type  
- Compared XGBoost and Random Forest performance  
- Tuned models using Bayesian optimization  
- Applied PCA to reduce multicollinearity and preserve 95% of variance

### 5. Ensembling
- Trained multiple models per segment  
- Aggregated predictions using the median  
- Applied a scaling factor to align predictions with real-world pricing levels

---

##  Challenges

- Incomplete and inconsistent data across years  
- Capturing geographic pricing trends without overfitting  
- Modeling temporal shifts in economic conditions  
- Balancing accuracy with interpretability

---
##  Credits

- Special thanks to my teammates **Daniel Mizrahi** and **Dvir Rehavi**  
- Together, we chose to treat this academic project as an opportunity to go beyond course expectations.  
- The greatest takeaway from this experience was the value of **collaboration** — working as a focused, aligned team made this project far more impactful than anything we could have done alone.

---



