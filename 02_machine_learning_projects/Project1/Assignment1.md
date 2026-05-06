# **Foundations of Machine Learning – Assignment 1**

This assignment consists of two major tasks involving **data cleaning**, **visualization**, **statistical hypothesis testing**, **correlation analysis**, and **linear regression modeling** using **scikit-learn**.
Datasets used:

* **Real Estate Price Prediction** dataset
* **Life Expectancy (WHO)** dataset

---

## **Task 1 — Real Estate Price Prediction**

### **Dataset**

Real estate dataset from Kaggle:
`https://www.kaggle.com/datasets/quantbruce/real-estate-price-prediction`

---

## **1.a — Data Exploration & Cleaning**

You should:

* Load the dataset and inspect missing values
* Handle missing data using appropriate imputation (e.g., mean, median, KNN)
* Remove inconsistencies or invalid records if needed
* Justify all decisions (e.g., “median imputation used due to skewed distribution”)

---

## **1.b — Data Visualization**

Create informative visualizations such as:

* Scatter plots (e.g., distance to MRT vs. unit price)
* Boxplots for outliers
* Histograms for distribution
* Correlation heatmap

Explain each finding clearly.
You may use **[https://www.data-to-viz.com](https://www.data-to-viz.com)** for ideas.

---

## **1.c — Hypothesis Testing**

### **i. Price per unit area vs. House Age (Above vs. Below Median Age)**

* Null Hypothesis (H₀): No difference in average price per unit area.
* Alternative Hypothesis (H₁): A significant difference exists.

Use **p-value method** (t-test).

---

### **ii. Price per Unit Area Across Convenience Store Counts**

* Use ANOVA if more than 2 categories.
* Null Hypothesis: Mean prices are equal across store count groups.
* Alternative Hypothesis: At least one group differs significantly.

---

### **iii. Association Between Two Categorical Variables**

* Choose any two categorical features (may categorize numerical ones).
* Use a **Chi-Square Test of Independence**.
* Report:

  * H₀: No association
  * H₁: Significant association exists

---

## **1.d — Correlation Analysis**

Compute correlation of each feature with:

```
Y — House price of unit area
```

Identify the variable **with the strongest influence**.

---

## **1.e — Linear Regression Model**

Using scikit-learn:

* Perform **train-test split**
* Fit a **simple linear regression**
* Extract coefficients (weights)
* Confirm whether the strongest predictor matches your correlation findings

---

---

# **Task 2 — Life Expectancy Dataset (WHO)**

### **Dataset**

Life Expectancy dataset from Kaggle:
`https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who`

---

## **2.a — Data Exploration & Visualization**

Repeat steps from Task 1:

* Clean missing data
* Impute values appropriately
* Generate visualizations to understand trends (e.g., life expectancy by region/year)

---

## **2.b — Hypothesis Testing**

### **i. Status vs. Disease Prevalence**

Example variable: *Hepatitis B vaccination rate*

* Use t-test or nonparametric alternative.
* H₀: No difference between Developed and Developing countries.

---

### **ii. Life Expectancy by Status**

Compare life expectancy between:

* Developed countries
* Developing countries
  (Method: Independent samples t-test)

---

### **iii. Life Expectancy Across Years**

* Use one-way ANOVA
* H₀: Life expectancy is the same across different years
* H₁: At least one year is different

---

### **iv. Two More Tests (Your Choice)**

Examples:

* Relationship between “Alcohol consumption” and “Life expectancy”
* Compare BMI differences across Status
* Association between Region and Disease prevalence
  (Chi-Square or ANOVA depending on variables)

---

## **2.c — Correlation with Target Variable**

Compute correlation between all predictors and:

```
Life expectancy
```

Rank variables by strength of correlation.

---

## **2.d — Country-Aware Train/Test Split**

Split such that **no country appears in both train and test**.

Train **two** linear regression models:

1. With the **Country** column
2. Without the **Country** column

Compare:

* Test performance
* Generalization
  Explain which approach is correct (Country as ID → should not be included).

---

## **2.e — Random Split Comparison**

Perform a random split and repeat the experiment.

Compare with part (d):

* Show why random split incorrectly inflates performance when “Country” leaks into both splits.

---

## **2.f — Linear Regression vs. L1-Regularized Model**

Train:

* Standard Linear Regression
* L1-regularized Linear Regression (Lasso)

Compare:

* Model weights
* Which features are shrunk to zero
* How the results align with correlation values from part (c)

---



