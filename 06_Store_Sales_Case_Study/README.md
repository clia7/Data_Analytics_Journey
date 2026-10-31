# Store Sales – Time Series Forecasting

![Python](https://img.shields.io/badge/Python-3.13-blue.svg)
![SQLite](https://img.shields.io/badge/SQLite-Database-blue?logo=sqlite)
![Scikit-Learn](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange)
![Kaggle](https://img.shields.io/badge/Dataset-Kaggle-blue?logo=kaggle)

## 📌 Project Overview
This project focuses on analyzing and forecasting retail sales for **Corporación Favorita**, a large Ecuador-based grocery retailer. By combining historical daily unit sales across **54 store locations** and **33 product families** with external socioeconomic signals—such as daily crude oil prices (`dcoilwtico`), national and regional holiday schedules, and transactional volumes—the goal is to build an end-to-end data science pipeline for accurate time-series forecasting.

---

## 🔄 Project Pipeline & Structure

The repository follows a structured 4-stage data science workflow:

### 🔹 1. Exploratory Data Analysis (EDA)
- **Data Auditing:** Evaluated over **3,000,888 training observations** across 7 relational datasets (`train.csv`, `test.csv`, `stores.csv`, `transactions.csv`, `oil.csv`, `holidays_events.csv`, and `sample_submission.csv`).
- **Data Quality & Structural Inspection:**
  - Standardized all temporal columns into native `datetime64` data structures.
  - Inspected store metadata across 54 unique stores spanning multiple Ecuadorian cities, states, store types (`A`–`E`), and geographic clusters.
- **Missing Value Identification:**
  - **Oil Prices (`oil.csv`):** Identified 43 missing values in the raw dataset (928,422 rows when merged with train data), primarily coinciding with non-trading days and public holidays.
  - **Transactions (`transactions.csv`):** Discovered 245,784 missing transaction entries (8.19% of train data across 7,448 store-date combinations).
  - **Holidays & Events Analysis:** Investigated missing transaction counts against national (e.g., *Primer día del año*, *Carnaval*, *Viernes Santo*), regional, and local events to determine store operating status and avoid misclassifying missing data as store closures.

### 🔹 2. Feature Engineering & Pre-Processing
- **Temporal Feature Extraction:** Generated granular calendar features including `year`, `month`, `day`, `day_of_week`, `day_of_year`, `quarter`, and a boolean `is_weekend` indicator.
- **Special Events & Transfer Handling:** Engineered an `is_special_date` flag to map national, regional, and local events while accounting for transferred public holidays.
- **Data Imputation & Leakage Management:**
  - **Oil Prices (`dcoilwtico`):** Applied forward-fill (`ffill()`) for ongoing time-series continuity, followed by backward-fill (`bfill()`) to address the leading edge (Jan 1, 2013). Documented the potential temporal leakage risks of backward-filling historical baseline points.
  - **Store Transactions:** Imputed missing transaction entries using store-specific median values (`groupby('store_nbr')['transactions'].transform(...)`), preserving individual store volume scales without introducing distortion.
- **Exporting Processed Datasets:** Saved the fully cleansed, 22-column feature-engineered dataset to `train_ml.csv` for model execution.

### 🔹 3. Machine Learning Model Training
- **Dataset Preparation:** Loaded the engineered `train_ml.csv` dataset comprising lag indicators, calendar metrics, store metadata, and oil price features.
- **Model Training & Evaluation:** Set up baseline regression and time-series forecasting algorithms (e.g., Scikit-Learn regressors) to predict future unit sales per product family and store.
- **Performance Verification:** Evaluated model outputs against validation splits using standard time-series evaluation metrics.

---

## ⚙️ Tech Stack & Tools

- **Languages:** Python (v3.13), SQL
- **Data Manipulation & Analytics:** Pandas, NumPy
- **Data Visualization:** Matplotlib, Seaborn
- **Machine Learning & Modeling:** Scikit-Learn
- **Environment:** Jupyter Notebook, Kaggle Platform

---
## 📝 My Monthly Reflection: October 2026

### 🚀 What went well?
- **Meticulous Data Quality Analysis:** Uncovered hidden patterns in missing values across oil prices and transactions rather than applying naive zero-imputations.
- **Structured Feature Pipeline:** Successfully transformed raw transactional and external macro data into a clean 22-feature modeling dataset (`train_ml.csv`).
- **Data Integrity Awareness:** Proactively identified and documented data leakage risks (e.g., using `bfill()` on time-series start dates).

### 🧠 Key Learnings
- **Time-Series Missingness vs. Closures:** Missing transaction values on holidays do not automatically mean zero sales; handling store-level medians prevents bias in non-closed outlets.
- **Relational Feature Integration:** Joining multi-level granular data (daily oil prices + daily store transactions + yearly calendar features) requires careful key alignment to prevent row multiplication.

### 🔄 What would I do differently next time?
- **Advanced Imputation:** Experiment with rolling-window averages or linear interpolation for crude oil prices instead of global back-fills.
- **Lag & Cyclical Features:** Incorporate explicit time-series lag features ($t-7$, $t-14$, $t-30$), rolling statistics, and trigonometric cyclic encoding (sine/cosine for months and days).
- **Automated Pipeline Scripts:** Modularize repetitive notebook preprocessing code into standalone `.py` scripts for cleaner execution.

---

## 🔮 Next Month's Goals (November 2026)
- **Interactive Dashboards:** Build an interactive **Streamlit** web application to visualize store performance, sales trends, and real-time model predictions.
- **Advanced ML & Tuning:** Explore tree-based gradient boosting models (XGBoost / LightGBM) and hyperparameter optimization techniques for time-series data.