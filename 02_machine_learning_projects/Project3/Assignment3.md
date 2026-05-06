#  **Foundations of Machine Learning – Assignment 3**

This assignment includes:

* A conceptual/theoretical section
* A practical NLP classification task for **emotion detection in Persian text**

---

#  **Part 1 — Theoretical Questions**

### **a) SVM Kernels: Linear, Polynomial, RBF, Sigmoid**

Explain and compare:

* **Linear kernel**: for linearly separable data
* **Polynomial kernel**: captures polynomial relationships
* **RBF kernel**: Gaussian similarity, powerful for nonlinear patterns
* **Sigmoid kernel**: related to neural activation functions

Discuss:

* Advantages & disadvantages
* When each kernel is preferred
* Computational considerations

---

### **b) CatBoost vs. LightGBM vs. XGBoost**

Compare:

* Handling of categorical features
* Tree-growing strategies (leaf-wise, depth-wise, symmetric trees)
* Speed, GPU support, memory usage
* Overfitting control
* Performance on large datasets
* CatBoost’s ordered boosting and target statistics
* LightGBM’s histogram-based optimization
* XGBoost’s regularization & split finding algorithms

---

### **c) Stratified k-Fold vs. Regular k-Fold**

Explain:

* Regular k-fold → random uniform splits
* Stratified k-fold → preserves label distribution
  State when stratification is necessary:
  ❗ Highly imbalanced classification
  ❗ Small datasets
  ❗ Avoiding label skew across folds

---

### **d) Validating Clustering Without Ground Truth**

Discuss challenges:

* No labels → must rely on internal/external metrics
  Metrics to explore:
* Silhouette score (acceptable: >0.25 good)
* Calinski–Harabasz
* Davies–Bouldin (lower is better)
* Domain knowledge to interpret clusters

---

### **e) Choosing Optimal K in Clustering**

Compare:

* **Elbow method**
* **Silhouette analysis**
* **Gap statistic**
  Explain strengths, weaknesses, and how to interpret each method.

---

### **f) Impact of k in k-Fold Cross-Validation**

Discuss:

* Small k → high bias, low variance
* Large k → low bias, high variance
* k=5 or k=10 → standard trade-off

---

### **g) Out-of-Bag (OOB) Error in Bagging**

Explain:

* How OOB samples (not used in bootstrap) estimate test error
* Why OOB reduces the need for a separate validation set

---

### **h) PCA in Genomics**

Discuss:

* High-dimensional genetic data
* PCA for dimensionality reduction
* Identification of population structure, batch effects, gene expression patterns

---

### **i) SVM in Anomaly Detection**

Cover:

* One-Class SVM
* Learning a decision boundary around normal data
* Applications: fraud detection, intrusion detection, rare event identification

---

---

#  **Part 2 — Persian Text Emotion Detection**

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


