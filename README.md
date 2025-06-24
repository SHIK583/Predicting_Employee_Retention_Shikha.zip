-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# 🧠 Employee Attrition Prediction Using Logistic Regression

This project focuses on building a predictive model to identify employee attrition using logistic regression. The workflow includes comprehensive preprocessing, exploratory analysis, feature engineering, and evaluation with industry-standard metrics.

---

## 📁 Project Overview

- **Dataset**: Employee-level data including demographic, job satisfaction, performance, and behavioral attributes
- **Objective**: Predict whether an employee is likely to leave or stay in the company
- **Model Used**: Logistic Regression

---

## ✅ Workflow Summary

### 1️⃣ Data Preprocessing

- Cleaned corrupted text fields (e.g., `"BacheloraEUR(tm)s Degree"` → `"Bachelor's Degree"`)
- Standardized categorical data using `unidecode`, `.strip()`, and `.title()`
- Dropped irrelevant columns (e.g., `Employee ID`)
- Handled missing values in `Distance from Home` and `Company Tenure (In Months)`

---

### 2️⃣ Exploratory Data Analysis (EDA)

#### 🔹 Univariate Analysis
- Visualized distributions of key categorical (`Job Role`, `Job Satisfaction`) and numerical features (`Monthly Income`, `Age`)

#### 🔹 Correlation Analysis
- Generated heatmaps to analyze multicollinearity between numeric features

#### 🔹 Class Balance Check
- Checked for imbalance in target variable (`Attrition`) using bar plots

#### 🔹 Bivariate Analysis
- Explored feature-wise attrition trends using boxplots and hue-based countplots

---

### 3️⃣ Feature Engineering

- Created dummy variables using `pd.get_dummies()` (one-hot encoding with `drop_first=True`)
- Scaled numerical features using `StandardScaler` to normalize ranges

---

### 4️⃣ Train–Test Split

- Split the dataset using `train_test_split()` with:
  - **70% training**
  - **30% validation**
  - `stratify=y` to maintain class balance

---

### 5️⃣ Model Building

#### 🔹 Logistic Regression
- Fit using `LogisticRegression(class_weight='balanced')`
- Handled class imbalance internally

#### 🔹 Optimal Threshold
- Used `precision_recall_curve()` to select a threshold beyond 0.5
- Selected cutoff where precision and recall were both strong

---

### 6️⃣ Model Evaluation

- **Accuracy**
- **Confusion Matrix** with calculation of:
  - True Positive (TP)
  - True Negative (TN)
  - False Positive (FP)
  - False Negative (FN)
- **Sensitivity** (Recall for 'Left')
- **Specificity** (Recall for 'Stayed')
- **Precision** and **Recall**
- **ROC-AUC Score**

---

## 📌 Key Takeaways

- Employees in roles with lower satisfaction and work-life balance showed higher attrition
- Model achieved balanced sensitivity and specificity after adjusting the cutoff
- Logistic regression provided interpretable insights into contributing factors

---

## 📂 Tech Stack

- Python (pandas, NumPy, sklearn, matplotlib, seaborn)
- Jupyter Notebook

---

