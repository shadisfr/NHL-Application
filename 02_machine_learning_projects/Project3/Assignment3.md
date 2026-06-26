#  **Foundations of Machine Learning – Assignment 3**



#   — Persian Text Emotion Detection

###  **Objective**

Perform **single-label** multiclass emotion classification on Persian text:

* Happiness
* Sadness
* Anger
* Fear
* Others

---

## ** 1. Data Cleaning & Feature Engineering**

Perform:

* Normalization of Persian text
* Removing diacritics, stopwords, URLs, emojis
* Tokenization / stemming or lemmatization
* Handling class imbalance if necessary
* Feature extraction:

  * Bag-of-Words
  * TF–IDF
  * Character n-grams

Document all steps and motivations in the notebook or a separate report.

---

## ** 2. Tree-Based Models**

Explore tree-based classifiers such as:

* Decision Tree
* Random Forest
* ExtraTrees
* XGBoost
* LightGBM
* CatBoost

Perform:

* Hyperparameter tuning
* Model pruning when applicable
* Performance comparison
* Interpretation of results

Summarize findings clearly.

---

## ** 3. Final Model**

Choose the best-performing classical model based on:

* Validation metrics
* Stability
* Interpretability

Justify the selection.

---

## ** 4. Model Evaluation**

Use appropriate metrics for multiclass emotion detection:

* Accuracy
* Precision, Recall, F1-score
* Confusion matrix

You may use:

* **k-fold cross-validation**
* **Stratified k-fold CV** (recommended for balanced class splits)

Provide interpretation of metric values.

---

## ** 5. Test Set Predictions**

You will be provided with:

* A test set **without true labels**

Tasks:

* Run inference using your final model
* Save predictions
* Ensure inference steps are fully documented so results are reproducible

---


