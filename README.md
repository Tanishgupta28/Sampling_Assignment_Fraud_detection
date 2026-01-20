
# Fraudulent Transaction Detection using Resampling Methods and Machine Learning

## 📘 Introduction

With the rapid growth of online payments, detecting **fraudulent credit card transactions** has become a critical challenge.
This project investigates how different **resampling strategies** combined with **machine learning algorithms** can improve fraud detection when dealing with **extremely skewed class distributions**.

Rather than relying on a single model, this study performs a **comparative analysis** to understand how sampling choices influence model performance.

---

## 🎯 Aim of the Study

- Analyze the effect of class imbalance on fraud detection models
- Balance minority and majority classes using **SMOTE**
- Generate multiple datasets using **distinct resampling techniques**
- Train and test various ML classifiers
- Determine the most effective model–sampling pair

---

## 🗂 Dataset Description

- **Dataset Name:** Credit Card Transactions Dataset
- **Total Observations:** 772
- **Input Features:**
  - 28 anonymized PCA-based variables (`V1`–`V28`)
  - Transaction time
  - Transaction amount
- **Output Label:**
  - `0` → Non-fraudulent transaction
  - `1` → Fraudulent transaction

---

## ⚠️ Problem Statement: Data Imbalance

### Initial Class Ratio

- Genuine transactions: **763 (≈98.8%)**
- Fraudulent transactions: **9 (≈1.2%)**

Such a disproportionate distribution leads to misleading accuracy if handled directly.

### Balanced Dataset using SMOTE

- Legitimate class: **763 samples**
- Fraud class: **763 samples**
- **Combined total:** 1,526 samples

SMOTE synthetically generates new fraud samples, enabling fairer training.

---

## 🔁 Experimental Pipeline

### Step 1: Data Understanding & Cleaning

- Loaded and explored the dataset
- Visualized class imbalance using bar charts
- Split data into features and target
- Applied SMOTE on training data only

---

### Step 2: Resampling Techniques Applied

| Technique            | Key Idea |
|----------------------|----------|
| Simple Random        | Random record selection |
| Stratified           | Preserves equal class proportions |
| Bootstrap            | Sampling with replacement |
| Systematic           | Picks every k-th entry |
| Cluster-based        | Sampling from grouped data |

Each technique creates a **unique training subset**, increasing experimental diversity.

---

### Step 3: Classification Models Used

The following algorithms were evaluated:

- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine (RBF)
- Gaussian Naive Bayes

All models were evaluated on the **same test split** to ensure unbiased comparison.

---

### Step 4: Evaluation Strategy

- Created **5 independent samples**
- Applied all **5 resampling techniques**
- Used **70% training and 30% testing split**
- Conducted **125 total experiments**

This approach minimizes randomness and strengthens conclusions.

---

## 📊 Results & Analysis

### Top Performing Combinations

| Model + Sampling Method              | Accuracy |
|-------------------------------------|----------|
| Random Forest + Stratified Sampling | **99.73%** |
| Random Forest + Random Sampling     | 99.46% |
| Random Forest + Bootstrap Sampling  | 99.46% |

---

### Best Resampling Method per Model

| Algorithm           | Best Technique        | Accuracy |
|---------------------|----------------------|----------|
| Logistic Regression | Bootstrap             | 94.55% |
| Decision Tree       | Random                | 98.64% |
| Random Forest       | Stratified            | **99.73%** |
| SVM                 | Bootstrap             | 73.02% |
| Naive Bayes         | Stratified            | 88.56% |

---

## 📐 Performance Metrics

Each experiment was assessed using:

- Accuracy score
- Confusion matrix
- Precision, recall, and F1-score

These metrics ensure balanced evaluation beyond simple accuracy.

---

## 🔎 Insights Gained

- Random Forest consistently shows superior performance
- Stratified resampling produces stable and realistic results
- Bootstrap sampling benefits simpler models
- SVM requires further tuning for imbalanced problems
- Sampling choice significantly impacts results

---

## 📌 Conclusion

This study demonstrates that **data resampling** combined with **appropriate machine learning models** plays a vital role in fraud detection systems.
The findings highlight the importance of preprocessing decisions in real-world classification tasks.

---

**Prepared by:** Tanish Gupta  
**Roll Number:** 102316041  
**Field:** Machine Learning | Data Science
