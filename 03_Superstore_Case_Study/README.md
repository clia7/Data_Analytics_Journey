# Superstore Analysis

This project is a comprehensive end-to-end data analysis and machine learning portfolio piece utilizing the Superstore dataset. The goal is to uncover actionable business insights regarding profitability, sales trends, and supply chain efficiency, followed by developing a predictive model to forecast transaction-level revenue. It also includes a dedicated SQL environment setup to practice querying and aggregating the data directly.

---

## 🔄 Project Pipeline & Structure

### 🔹 1. Exploratory Data Analysis 
Analyzed sales, profitability, and customer segments to identify key performance drivers. Discovered that the Technology category generates the highest profits, while extreme discounting (up to 80%) in Office Supplies heavily damages overall margins. Identified strong seasonal sales peaks in Q4 and a consistent 4-day shipping average across all product categories.

### 🔹 2. Feature Engineering & Pre-Processing
Transformed the raw dataset into a machine-learning-ready format. Extracted date components (`Order_Year`, `Order_Month`, `Order_DayOfWeek`), calculated `Shipping_Days` as a quantifiable supply chain KPI, and engineered behavioral flags like `is_weekend_order` and `is_profitable`. Applied one-hot encoding to categorical variables and removed direct identifiers to prevent data leakage.

### 🔹 3. Machine Learning Model Training 
Built regression models to forecast transaction-level sales. Split the engineered dataset (80/20) and trained both Random Forest and Gradient Boosting Regressors. Evaluated the models based on MAE, RMSE, and R² scores, identifying `Quantity`, `Sub-Category_Copiers`, and `Order_Month` as the top predictors for revenue.

---

## ⚙️ Tech Stack & Tools
* **Languages:** Python, SQL (SQLite)
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn
* **Environment:** Jupyter Notebooks, IPython SQL

---

## 🛠️ Machine Learning Pipeline & Results
Two primary models were trained to predict sales amounts:
* **Random Forest Regressor:**
  * MAE: $212.91
  * RMSE: $673.04
  * R² Score: 0.2331
* **Gradient Boosting Regressor:**
  * MAE: $198.83
  * RMSE: $677.73
  * R² Score: 0.2224

*Insight:* While the Gradient Boosting model slightly minimized the absolute error, both models exhibit a low R² score. This indicates that the current features explain only about 22-23% of the variance in sales, highlighting the difficulty of predicting exact revenue on highly dispersed transactional data.

---

## 📝 My Monthly Reflection: July 2026

### 🚀 What went well?


### 🧠 Key Learnings


### 🔄 What would I do differently next time?


---

### 🔮 Next Month's Goals (August 2026)
1. **Merge with Python:** 
2. **Hyperparameter adjustment:** 