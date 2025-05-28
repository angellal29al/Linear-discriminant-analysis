# 🐚 Scallop Sex Prediction Using Discriminant Analysis

## 📌 Objective

This project aims to **predict the sex of scallops** using **physical measurements**—a task that traditionally requires a tedious and time-consuming microscopic process. By using machine learning models like **Linear Discriminant Analysis (LDA)** and **Quadratic Discriminant Analysis (QDA)**, we attempt to automate and improve this classification problem.

---

## 📂 Dataset Description

The dataset contains physical measurements of scallops, along with their sex. The attributes are:

| Feature            | Type       | Description                                   |
|--------------------|------------|-----------------------------------------------|
| `Sex`              | Nominal    | Target variable: 0 - Female, 1 - Male         |
| `Length`           | Continuous | Longest shell measurement (mm)                |
| `Diameter`         | Continuous | Perpendicular to length (mm)                  |
| `Height`           | Continuous | With meat in shell (mm)                       |
| `Whole weight`     | Continuous | Whole abalone weight (g)                      |
| `Shucked weight`   | Continuous | Weight of meat (g)                            |
| `Viscera weight`   | Continuous | Gut weight after bleeding (g)                 |
| `Shell weight`     | Continuous | Shell weight after being dried (g)            |

---

## 🔍 Exploratory Data Analysis (EDA)

Several visualizations and analyses were performed:

- 📊 **Countplot**: Revealed class imbalance with ~64% Female and ~36% Male.
- 📈 **Line Graphs**: Indicated that none of the variables follow a normal distribution.
- 🧰 **Box Plots**: Showed that all variables contain outliers.

---

## ⚖️ Handling Class Imbalance

To correct the class imbalance, **SMOTE (Synthetic Minority Oversampling Technique)** was applied.

- 📌 **Length of oversampled data**: 3680 samples  
- 👩‍🔬 **Number of Females**: 1840  
- 👨‍🔬 **Number of Males**: 1840  
- 📊 **Proportion after SMOTE**:  
  - Females: 0.5  
  - Males: 0.5

---

## 🤖 Models Applied

### 🧪 Model 1: Linear Discriminant Analysis (LDA)

Before applying LDA, we tested for **multivariate normality**:

- **H₀**: The data is not significantly different from a multivariate normal distribution.
- **H₁**: The data is significantly different from a multivariate normal distribution.

### 🧪 Model 2: Quadratic Discriminant Analysis (QDA)

Also applied to compare performance with LDA under the same conditions.

---

## 📊 Model Evaluation

| Metric      | LDA       | QDA       |
|-------------|-----------|-----------|
| Accuracy    | 63.35%    | 61.91%    |
| Precision   | 61%       | 59%       |
| F1-Score    | ✅ Higher | ❌ Lower  |

✅ **Conclusion**: LDA performed better in accuracy, precision, and F1-score.  
This may be due to LDA's robustness even when normality assumptions are slightly violated.


### Required Libraries:

Python 3.x

pandas

numpy

seaborn

matplotlib

scikit-learn

imbalanced-learn

## ✅ Conclusion
This project demonstrates how machine learning can automate a biological classification task traditionally performed manually. By using physical features of scallops:

We balanced the dataset using SMOTE.

Applied LDA and QDA models for classification.

Found that LDA outperforms QDA, with an accuracy of 63.35%.

## 🚀 Future Work
Explore more advanced classifiers like Random Forest, XGBoost, or SVM

Implement feature selection or dimensionality reduction

Build a Streamlit or Flask app for real-time predictions

Perform hyperparameter tuning for better model performance
