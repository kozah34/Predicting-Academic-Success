# Predicting Academic Success: A Regression Analysis

**Authors:** Derrick Nyagesuka & Baysa Wakjira  
**Course:** STAT 311 - Regression Analysis (Fall 2025)  
**Tools:** JMP, Excel, Kaggle Datasets

## 📌 Project Overview
[cite_start]The primary objective of this research was to identify the most significant predictors of student academic performance[cite: 13, 329]. [cite_start]Using a dataset of over 6,500 student records, we applied multiple linear regression techniques to quantify how factors like study habits, parental involvement, and sleep schedules influence final exam scores[cite: 16, 29].

[cite_start]Our goal was to answer the question: *"How do individual habits compare against environmental factors when predicting success?"*[cite: 14].

## 📂 Data Description
[cite_start]The data was sourced from the **Student Performance Factors** dataset on Kaggle[cite: 20].
- **Original Size:** 6,607 observations with 20 predictors.
- [cite_start]**Cleaning:** We performed listwise deletion on 78 rows containing null values in the `Teacher_Quality` column[cite: 22, 28].
- [cite_start]**Final Sample Size:** 6,529 observations[cite: 29].
- [cite_start]**Target Variable:** `Exam_Score` (Continuous)[cite: 23].

**Key Predictors:**
* [cite_start]**Academic:** Hours Studied, Attendance, Previous Scores[cite: 26].
* [cite_start]**Environmental:** Parental Involvement, Access to Resources, Teacher Quality[cite: 26].
* [cite_start]**Personal:** Sleep Hours, Motivation Level[cite: 27].

## ⚙️ Methodology
[cite_start]The analysis was conducted using **JMP Software** [cite: 146] following this pipeline:

1.  **Exploratory Data Analysis (EDA):** Analyzed distributions and checked for linearity using scatterplot matrices. [cite_start]We identified strong positive correlations between `Attendance` (r=0.58) and `Exam_Score`[cite: 88, 141].
2.  [cite_start]**Data Partitioning:** Utilized an **80/20 Train/Validation split** to prevent overfitting[cite: 153].
3.  **Model Building:**
    * [cite_start]**Full Model:** Included all 8 predictors ($R^2 = 0.666$)[cite: 181].
    * [cite_start]**Reduced Model:** Removed `Sleep_Hours` as it was statistically insignificant ($p > 0.05$)[cite: 190, 284].
    * [cite_start]**Diagnostics:** Tested for curvilinear relationships ($Hours^2$) and interactions ($Hours \times Motivation$), but retained the linear reduced model for parsimony[cite: 217, 246].

## 📊 Key Results
[cite_start]Our final model explained approximately **66.53% of the variance** in exam scores ($R^2_{adj} = 0.6653$) with an RMSE of **2.24**[cite: 280, 281].

| Feature | Impact (Coefficient) | Significance |
| :--- | :--- | :--- |
| **Attendance** | +0.199 points per % | [cite_start]$p < .0001$ [cite: 282] |
| **Hours Studied** | +0.297 points per hour | [cite_start]$p < .0001$ [cite: 283] |
| **Parental Involvement** | High involvement > Low | [cite_start]$p < .0001$ [cite: 334] |
| **Sleep Hours** | No significant impact | [cite_start]$p = 0.9156$ [cite: 284, 336] |

**Conclusion:**
Consistent effort (Attendance/Study Hours) is the strongest predictor of success, outweighing innate ability. [cite_start]Surprisingly, variations in sleep schedules did not statistically impact scores when other factors were controlled[cite: 332, 335].

## 📉 Limitations
* [cite_start]**Residual Normality:** The model tends to underpredict scores for top-performing students (outliers), resulting in a deviation from normality in the residual plot[cite: 308].
* [cite_start]**Causality:** As this is observational data, we can identify correlations but cannot definitively prove causation[cite: 339].

## 🚀 How to View
1.  **Report:** View the full PDF report `Predicting Academic Success.pdf` for detailed statistical breakdowns.
2.  **Presentation:** See `Presentation1.pdf` for the slide deck summary.
3.  **JMP:** The analysis files are compatible with JMP Student Edition.

---
[cite_start]*This project was completed for Dr. Iresha Premarathna's STAT 311 class.* [cite: 6]
