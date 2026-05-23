# 🚢 Titanic - Machine Learning from Disaster

This is my first full end-to-end machine learning project. I created this project as part of my monthly learning routine. 

---

## 📊 Project Overview
The goal of this project is to analyze the historic Titanic passenger data and train machine learning models to predict whether a passenger survived the disaster or not. It transitions from exploratory data analysis (EDA) to feature engineering and model evaluation.

## 🔄 Project Iterations
* **Standard Dataset:** My intial run using basic cleaned features to established initial model 
* **Detailed Datased (-b Files):** My second run. Here I expand the dataset to over 40 columns to check if it is possible to improve the model predictions

## ⚙️ Tech Stack & Tools
* **Environment:** VS Code🖥️
* **Libraries:** 
  * Data Handling & EDA: `pandas`, `numpy`, `matplotlib`, `seaborn` 📊
  * Machine Learning: `scikit-learn` (Logistic Regression, Random Forest, KNN)
  * Metrics: `accuracy_score`

---

## 🛠️ The Machine Learning Pipeline

1. **Exploratory Data Analysis (EDA):**
   * Investigating missing values, checking class distributions, and understanding passenger demographics.
2. **Feature Engineering:**
   * Preparing the dataset for ML algorithms by handling categorical variables and extracting relevant features.
3. **Model Selection & Evaluation:**
   * Splitting the data strictly into `X_train`, `X_test`, `y_train`, and `y_test` to prevent **Data Leakage**.
   * Training and comparing three different classifiers.

### Current Model Standings (Baseline)
| Model | Current Accuracy | Notes |
| :--- | :--- | :--- |
| **Logistic Regression** 📈 | **%** | Top baseline performer. Currently evaluating coefficients to understand feature impact. |
| **Random Forest** 🌲 | **%** | Strong, stable performance. Highly robust against overfitting. |
| **K-Nearest Neighbors (KNN)** 🤖 | **%** | Solid baseline using neighbor-based spatial classification. |

---

## 📝 My Monthly Reflection: May 2026

### 🚀 What went well?

### 🧠 Key Learnings

### 🔄 What would I do differently next time?


### 🔮 Next Month's Goals (June 2026)
1. **Robust Code:** Implement `try-except` exception handling blocks to safely secure data loading paths.
2. **Advanced Visualization:** Introduce **Power BI** into the workflow to take data storytelling and dashboarding to the next level.