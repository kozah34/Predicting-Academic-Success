# Predicting Academic Success: A Regression Analysis

**Authors:** Derrick Nyagesuka & Baysa Wakjira
**Course:** STAT 311 - Regression Analysis (Fall 2025)
**Tools:** JMP, Excel, Kaggle Datasets

## 📌 Project Overview
The primary objective of this research was to identify the most significant predictors of student academic performance. Using a dataset of over 6,500 student records, we applied multiple linear regression techniques to quantify how factors like study habits, parental involvement, and sleep schedules influence final exam scores.

Our goal was to answer the question: *"How do individual habits compare against environmental factors when predicting success?"*

## 📂 Data Description
The data was sourced from the **Student Performance Factors** dataset on Kaggle.
- **Original Size:** 6,607 observations with 20 predictors.
- **Cleaning:** We performed listwise deletion on 78 rows containing null values in the `Teacher_Quality` column.
- **Final Sample Size:** 6,529 observations.
- **Target Variable:** `Exam_Score` (Continuous).

**Key Predictors:**
* **Academic:** Hours Studied, Attendance, Previous Scores.
* **Environmental:** Parental Involvement, Access to Resources, Teacher Quality.
* **Personal:** Sleep Hours, Motivation Level.

## ⚙️ Methodology
The analysis was conducted using **JMP Software** following this pipeline:

1.  **Exploratory Data Analysis (EDA):** Analyzed distributions and checked for linearity using scatterplot matrices. We identified strong positive correlations between `Attendance` (r=0.58) and `Exam_Score`.
2.  **Data Partitioning:** Utilized an **80/20 Train/Validation split** to prevent overfitting.
3.  **Model Building:**
    * **Full Model:** Included all 8 predictors.
    * **Reduced Model:** Removed `Sleep_Hours` as it was statistically insignificant (p > 0.05).
    * **Diagnostics:** Tested for curvilinear relationships (Hours Squared) and interactions (Hours * Motivation), but retained the linear reduced model for parsimony.

## 📊 Key Results
Our final model explained approximately **66.53% of the variance** in exam scores (Adjusted R-squared = 0.6653) with an RMSE of **2.24**.

| Feature | Impact (Coefficient) | Significance |
| :--- | :--- | :--- |
| **Attendance** | +0.199 points per % | p < .0001 |
| **Hours Studied** | +0.297 points per hour | p < .0001 |
| **Parental Involvement** | High involvement > Low | p < .0001 |
| **Sleep Hours** | No significant impact | p = 0.9156 |

**Conclusion:**
Consistent effort (Attendance/Study Hours) is the strongest predictor of success, outweighing innate ability. Surprisingly, variations in sleep schedules did not statistically impact scores when other factors were controlled.

## 📉 Limitations
* **Residual Normality:** The model tends to underpredict scores for top-performing students (outliers), resulting in a deviation from normality in the residual plot.
* **Causality:** As this is observational data, we can identify correlations but cannot definitively prove causation.

## 🚀 How to View
1.  **Report:** View the full PDF report `Predicting Academic Success.pdf` for detailed statistical breakdowns.
2.  **Presentation:** See `Presentation1.pdf` for the slide deck summary.
3.  **JMP:** The analysis files are compatible with JMP Student Edition.

---
*This project was completed for Dr. Iresha Premarathna's STAT 311 class.*
