# **Foundations of Machine Learning – Assignment 2**


This assignment contains two parts:

1. A conceptual/theoretical section
2. A practical binary-classification task using the **Titanic–Spaceship dataset**

---

# **Part 1 — Theoretical Questions**

### **a) Bias–Variance Tradeoff**

Write the formal mathematical formulation and explain how:

* Bias measures model flexibility
* Variance measures model sensitivity
* Irreducible error affects total prediction error

---

### **b) Logistic Regression vs. Linear Discriminant Analysis**

Discuss:

* When **logistic regression** performs better
  (e.g., nonlinear class boundaries, fewer distributional assumptions)
* When **LDA** performs better
  (e.g., Gaussian class-conditional distributions, shared covariance matrix)

---

### **c) Curse of Dimensionality in KNN**

Explain:

* Distance concentration in high dimensions
* Reduced discrimination between nearest and farthest neighbors
* Need for dimensionality reduction or feature selection

---

### **d) Nested Cross-Validation**

Describe:

* Inner loop: model/parameter selection
* Outer loop: unbiased generalization error estimate
* Why nested CV prevents information leakage

---

### **e) Elastic Net (L1 + L2 Combination)**

Explain:

* How combining Lasso (L1) and Ridge (L2) affects classification
* Intuition behind L1 vs. L2 norms
* What happens if using Norm-p or Norm-∞ instead
  (e.g., geometry of constraint regions, sparsity behavior)

---

### **f) Bootstrap for Standard Error Estimation** *(extra point)*

Discuss how:

* Bootstrapping repeatedly resamples data
* Computes mean for each resample
* Estimates standard error from the distribution of bootstrap means

---

### **g) Bias–Variance Analysis Using Cross-Validation** *(extra point)*

Explain how:

* CV error patterns illustrate underfitting vs. overfitting
* Helps understand model complexity effects

---

---

# **Part 2 — Titanic Spaceship Classification Task**

### **Objective**

Perform a **binary classification task** using the **Spaceship Titanic dataset**.
You must apply your knowledge of data exploration, cleaning, modeling, and evaluation.

---

### ** 1. Exploratory Data Analysis (EDA)**

Conduct EDA to understand:

* Distribution of numerical variables
* Categorical feature patterns
* Missing data structure
* Correlations
* Potential useful transformations or new features

Use visualizations where appropriate.

---

### ** 2. Data Cleaning & Feature Engineering**

Tasks include:

* Handling missing data
* Encoding categorical variables
* Normalizing/standardizing numerical features
* Creating new features (e.g., cabin groups, spending categories)
* Document **every step and justification** in your notebook or a separate report
  (e.g., “We used median imputation due to skewness in the feature distribution.”)

---

### ** 3. Model Training and Evaluation**

Train **at least one classification model** (e.g., Logistic Regression, Random Forest, SVM):

You must:

1. Train the model **before** feature engineering
2. Train the model **after** feature engineering
3. Compare performance to demonstrate the effect of your modifications

---

### ** 4. Cross-Validation & Ablation Study**

* Use **cross-validation** to evaluate model performance
* Conduct an **ablation study** (remove or add features and evaluate their impact)
* Discuss which features helped or hurt performance and why






