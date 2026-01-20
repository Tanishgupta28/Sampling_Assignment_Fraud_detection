
# Credit Card Fraud Detection with Sampling Strategies and ML Models

## 📌 Project Description

This project studies the problem of **credit card fraud detection** using machine learning on a **highly imbalanced dataset**.
Because fraudulent transactions are extremely rare compared to genuine ones, different **data sampling techniques** are applied and their impact on multiple **classification algorithms** is analyzed.

The objective is to determine **which sampling method–model combination performs best** for detecting fraud reliably.

---

## 🎯 Project Goals

- Address extreme class imbalance in transaction data
- Use **SMOTE (Synthetic Minority Oversampling Technique)** to balance the dataset
- Experiment with **multiple sampling approaches**
- Train and evaluate **various machine learning models**
- Compare results and identify optimal configurations

---

## 📊 Dataset Overview

- **Dataset:** Credit Card Transactions
- **Number of Records:** 772
- **Features:**
  - 30 numerical attributes
  - PCA-transformed features `V1`–`V28`
  - Additional fields: `Time`, `Amount`
- **Target Column:**
  - `0` → Normal transaction
  - `1` → Fraudulent transaction

---

## ⚖️ Class Imbalance Problem

### Original Distribution

- Class 0 (Legitimate): **763 records (98.8%)**
- Class 1 (Fraud): **9 records (1.2%)**

Such imbalance causes models to bias heavily toward the majority class.

### After Applying SMOTE

- Class 0: **763 samples**
- Class 1: **763 samples**
- **Total Samples:** 1,526

SMOTE creates **synthetic minority samples**, enabling balanced learning without data duplication.

---

## 🔄 Methodology

### 1️⃣ Data Exploration & Preparation

- Loaded and inspected the dataset
- Analyzed class distribution using visual plots
- Split features (`X`) and labels (`y`)
- Applied SMOTE only on training data
- Generated a balanced dataset for experiments

---

### 2️⃣ Sampling Techniques Used

| Method               | Purpose                          |
|----------------------|----------------------------------|
| Random Sampling      | Random subset selection          |
| Stratified Sampling  | Maintains class proportions      |
| Bootstrap Sampling   | Sampling with replacement        |
| Systematic Sampling  | Selects every k-th instance      |
| Cluster Sampling     | Sampling based on data clusters  |

Each method produces a different training subset from the balanced data.

---

### 3️⃣ Machine Learning Algorithms

The following models were trained and tested:

- Logistic Regression
- Decision Tree
- Random Forest
- Support Vector Machine (RBF Kernel)
- Gaussian Naive Bayes

All models were evaluated on a **common test set** to ensure fairness.

---

### 4️⃣ Experimental Setup

- Generated **5 random samples** (80% each)
- Applied all **sampling techniques** on each sample
- Used a **70:30 train–test split**
- Total experiments:
  **5 × 5 × 5 = 125 model runs**

This reduces randomness and improves result reliability.

---

## 📈 Performance Summary

### 🏆 Best Overall Results

| Configuration                                    | Accuracy |
|-------------------------------------------------|----------|
| Stratified Sampling + Random Forest              | **99.73%** |
| Random Sampling + Random Forest                  | 99.46%   |
| Bootstrap Sampling + Random Forest               | 99.46%   |

---

### ✅ Best Sampling Method per Model

| Model               | Best Sampling Technique | Accuracy |
|---------------------|-------------------------|----------|
| Logistic Regression | Bootstrap Sampling      | 94.55%   |
| Decision Tree       | Random Sampling         | 98.64%   |
| Random Forest       | Stratified Sampling     | **99.73%** |
| SVM                 | Bootstrap Sampling      | 73.02%   |
| Naive Bayes         | Stratified Sampling     | 88.56%   |

---

## 📊 Evaluation Metrics

For every experiment, the following metrics were computed:

- Accuracy
- Confusion Matrix
- Precision, Recall, and F1-score

These metrics help analyze both **fraud detection capability** and **false alarm rates**.

---

## 🔍 Observations

- **Random Forest** consistently outperforms other models
- **Stratified Sampling** provides stable and reliable results
- **Bootstrap Sampling** benefits linear models
- **SVM** shows comparatively weak performance
- Sampling impact varies depending on model architecture

---

## 🧠 Key Learnings

- Handling class imbalance is critical in fraud detection
- Sampling strategies significantly influence model performance
- Tree-based models are more robust to data variations
- Accuracy alone is insufficient—confusion matrices matter

---

## 📌 Final Remarks

This project highlights the importance of combining **sampling techniques** with **machine learning models** to improve performance on imbalanced datasets.
The workflow and results can be extended to other real-world fraud detection problems.

---

**Author:** Tanish Gupta (**102316041**)  
**Domain:** Machine Learning | Data Science | Fraud Detection
