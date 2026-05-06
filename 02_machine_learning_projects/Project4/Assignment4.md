# Click-Through Rate (CTR) Prediction Assignment

Click-Through Rate (CTR) prediction is a fundamental problem in **online advertising**, directly influencing both **platform revenue** and the effectiveness of **marketing campaigns**.
In this assignment, you will analyze user interaction data to predict whether a user will **click on an online advertisement**.

---

## Dataset Description

The dataset contains **10 columns**:

* **9 columns**: user and session-level features (e.g., demographics, browsing behavior, timestamps, etc.)
* **Target column**:

  * `Clicked on Ad` — a binary variable indicating whether the user clicked (1) or did not click (0) on the ad.

Your goal is to build and evaluate models that **predict `Clicked on Ad`**.

---

## 1. Exploratory Data Analysis (EDA)

You must perform **rich EDA** and compose a **comprehensive report** (separate document) that includes:

* Overview of dataset size, feature types (numeric, categorical)
* Missing values and anomalies
* Distribution analysis of key features
* Relationship between features and `Clicked on Ad`
* Class balance of the target variable
* Visualizations such as:

  * Histograms / KDE plots
  * Boxplots
  * Correlation heatmap
  * Bar plots for categorical variables
  * Plots showing differences between clicked vs. non-clicked users



---

## 2. Data Cleaning & Feature Engineering

In your **Jupyter notebook**, you should:

* Handle missing values (e.g., imputation, removal)
* Detect and treat outliers if necessary
* Encode categorical variables (e.g., one-hot encoding, label encoding)
* Scale or normalize numerical features if needed
* Create meaningful derived features (e.g., time-based features, interaction terms, bucketed ages, etc.)

For each step, **document and justify your decisions**, for example:

* Why a specific imputation strategy was chosen
* Why certain features were transformed or removed
* How feature engineering improved model interpretability or performance

---

## 3. CTR Classification Models

Implement and compare **one or more classification algorithms** for predicting `Clicked on Ad`, such as:

* Logistic Regression
* Decision Tree
* Random Forest
* Gradient Boosting / XGBoost / LightGBM
* Support Vector Machines

For each model:

* Train the model on the processed dataset
* Evaluate using **appropriate metrics**, for example:

  * Accuracy
  * Precision, Recall, F1-score
  * ROC–AUC
  * Confusion matrix

Compare the performance of different algorithms and summarize:

* Which model performed best and why
* How complex models compare to simpler baselines

---

## 4. Cross-Validation & Model Evaluation

Use **cross-validation** to obtain more reliable estimates of model performance:

* Apply **k-fold cross-validation** (e.g., k=5 or k=10)
* Report mean and standard deviation of key metrics across folds
* Discuss:

  * Stability of model performance
  * Whether there is overfitting or underfitting
  * How cross-validation results influenced your choice of final model

---

## Suggested Workflow

1. Load and understand the dataset
2. Perform EDA and write the report with plots
3. Clean and preprocess the data
4. Engineer features that may improve predictive power
5. Train several models and tune basic hyperparameters
6. Evaluate using cross-validation
7. Select and justify the final model

---

