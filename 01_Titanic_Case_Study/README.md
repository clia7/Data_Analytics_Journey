# 🚢 Titanic - Machine Learning from Disaster

This is my first full end-to-end machine learning project, developed as part of my structured monthly learning routine. It tracks my progress as I transition from rigorous exploratory data analysis (EDA) to feature engineering and model evaluation.

---

## 🔗 Quick Links & Project Showcase
* **📊 View the Notebook on Kaggle:** [![Kaggle](https://img.shields.io/badge/Kaggle-00F5D4?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/code/cliaa74/titanic-survival-prediction)
* **💻 View Full Project Code on GitHub:** [![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/clia7/Titanic_Survival_Prediction/tree/main)

---

## 📊 Project Overview
The goal of this project is to analyze the historic Titanic passenger data and train machine learning models to predict passenger survival. The project is explicitly designed as an iterative pipeline, proving that deep data analysis and smart feature selection are far more valuable than simply feeding a model a large volume of raw data.

## 🔄 Project Iterations

### 🔹 1. Standard Dataset (First Run: `01`, `02`, `03` Files)
* **Approach:** Basic data cleaning and straightforward feature encoding. Missing ages were filled with a global median, and categorical variables (`Sex`, `Embarked`) were converted directly into dummy variables.
* **Result:** Established a solid baseline dataset with **26 columns**, but the models suffered from unrefined features and general noise.

### 🔹 2. Detailed Dataset (Second Run: `01b`, `02b`, `03b` V2 Files)
* **Approach:** Advanced feature engineering and targeted data transformations based on demographic insights:
  * **Title-Based Age Imputation:** Extracted passenger titles (*Mr, Mrs, Miss, Master*) to impute missing ages based on specific peer-group medians instead of a blind global average.
  * **Socio-Economic Grouping:** Engineered a `Ticket_Group` feature using ticket numbers to identify passengers traveling together beyond immediate family sizes.
  * **Feature Binning:** Grouped continuous values into categorical bins (`Age_Groups` and `Fare_Categories`) to safely handle extreme price outliers (up to $500) and prevent overfitting.
  * **Feature Selection (The "Slim" Run):** Dropped 13 redundant or noisy dummy columns, narrowing the dataset down from 40 to 27 highly predictive features to actively fight overfitting.

---

## ⚙️ Tech Stack & Tools
* **Environment:** VS Code 🖥️ & Jupyter Notebooks
* **Libraries:** 
  * Data Handling & EDA: `pandas`, `numpy`, `matplotlib`, `seaborn` 📊
  * Machine Learning: `scikit-learn` (`LogisticRegression`, `RandomForestClassifier`, `KNeighborsClassifier`)
  * Validation Metrics: `accuracy_score`

---

## 🛠️ The Machine Learning Pipeline & Results

### 📊 Validation Set Performance Standings

| Model Classifier | Iteration 1 (Baseline / 26 Cols) | Iteration 2 (Detailed / 40 Cols) | Iteration 2 (Slim Run / 27 Cols) | Strategic Note |
| :--- | :---: | :---: | :---: | :--- |
| **Logistic Regression** 📈 | 80.45% | 81.56% | **86.03%** | **Top Performer.** Dropping 13 noisy features fixed overfitting and unlocked a **+4.47%** accuracy boost. |
| **Random Forest** 🌲 | 78.21% | 78.21% | **77.65%** | Highly robust baseline, but slightly degraded when losing specific granular information in the slim run. |
| **K-Nearest Neighbors** 🤖 | 73.18% | 81.56% | **79.33%** | Severely struggled with high-dimensional dummy noise; heavily dependent on compact feature space. |

---

## 📝 My Monthly Reflection: May 2026

### 🚀 What went well?
* **Data-Driven Feature Pruning:** Successfully optimized the pipeline by identifying and dropping 13 noisy dummy variables. Reducing the features from 40 to 27 actively fixed overfitting and directly triggered a **+4.47%** accuracy boost for the Logistic Regression model.

### 🧠 Key Learnings
* **Median vs. Mean:** Using the *median* is crucial when dealing with heavily skewed numerical data containing extreme outliers (like the luxury fares in 1st class).

### 🔄 What would I do differently next time?
* **Git Commits:** Implement smaller, more frequent commits with clear messages rather than pushing massive chunk updates all at once.

---

### 🔮 Next Month's Goals (June 2026)
1. **Robust Engineering:** Implement `try-except` exception handling to secure data loading paths and handle unexpected file issues.
2. **Advanced Visualization:** Introduce **Power BI** into the workflow to create interactive business dashboards and elevate data storytelling.