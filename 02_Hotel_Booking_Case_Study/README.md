# 🏨 Hotel Booking Cancellation Prediction

This end-to-end machine learning project focuses on analyzing hotel demand patterns and building predictive models to forecast booking cancellations. Developed as part of my structured monthly learning routine, it highlights my transition from exploratory data analysis (EDA) to feature engineering and preparing datasets for machine learning.

---

## 📊 Project Overview
The goal of this project is to tackle a classic revenue management problem in the hospitality industry: predicting whether a guest will cancel their booking (`is_canceled`). High cancellation rates directly impact hotel revenue and room allocation strategies. 

Rather than throwing raw data directly into a model, this project showcases an iterative data pipeline where exploratory data insights drive custom feature engineering, rigorous handling of missing values, and systematic data leakage prevention.

---

## 🔄 Project Pipeline & Structure

### 🔹 1. Exploratory Data Analysis (`01_Hotel_Booking_EDA.ipynb`)
* **Objective:** Understand customer behavior, distribution channels, and booking patterns.
* **Key Achievements:**
  * Analyzed market segments, identifying Online Travel Agencies (OTAs) as the primary booking driver but also the source of high cancellation volumes.
  * Investigated customer loyalty trends, showing an exceptionally low rate of returning guests.
  * Explored geographic market concentrations, locating the primary customer base in Western Europe (Portugal, Great Britain, France, Spain, Germany).
* **Additional Insight (2nd Iteration Split Analysis - `01b_Hotel_Booking_EDA_V2.ipynb`):** Converted the EDA into a comparative scenario analysis during the second iteration by splitting the data into two distinct pipelines (with and without duplicates). This revealed that the 31,994 duplicate entries were heavily driven by large-scale bulk group bookings within the *Groups* and *Offline TA/TO* segments that were canceled simultaneously, rather than random data anomalies.

### 🔹 2. Feature Engineering & Pre-Processing (`02_Hotel_Booking_FE.ipynb` & `02b_Hotel_Booking_FE_V2.ipynb`)
* **Objective:** Clean, transform, and structure the data into an optimized format for Machine Learning.
* **Key Achievements:**
  * **Data Leakage Prevention:** Identified and dropped `reservation_status` and `reservation_status_date`. Since these columns contain post-booking outcomes (like 'Canceled' or 'No-Show' timestamps), including them would cause severe data leakage and unrealistic model performance.
  * **Domain-Specific Aggregations:** Engineered a `total_stay_length` feature and combined it with the Average Daily Rate (`adr`) to calculate the financial impact via `booking_value`. Calculated `total_pax` to evaluate group sizes.
  * **Smart Categorical Encoding:** Transformed ID-heavy, sparse features (`agent`, `company`) into lightweight, binary markers (`has_agent`, `has_company`) using type-casting (`.astype(int)`).
  * **Ordinal & One-Hot Encoding:** Applied structured dictionary mapping to convert textual months into chronological numbers (`arrival_date_month_numb`). Used `pd.get_dummies()` to seamlessly expand nominal text features (`hotel`, `meal`, `market_segment`, etc.) into machine-readable numeric spaces.

### 🔹 3. Machine Learning Model Training (`03_Hotel_Booking_ML.ipynb` & `03b_Hotel_Booking_ML_V2.ipynb`)
* **Objective:** Train classification models and compare the performance between the deduplicated and non-deduplicated datasets.
* **Key Achievements:**
  * Evaluated Logistic Regression and Random Forest models on the original dataset (with duplicates).
  * In the second iteration, implemented an XGBoost Classifier and compared it against the Random Forest model on the strict, deduplicated dataset.

---

## ⚙️ Tech Stack & Tools
* **Environment:** Jupyter Notebooks 🖥️ / VS Code
* **Libraries:** * Data Handling & EDA: `pandas`, `numpy`, `matplotlib`, `seaborn` 📊
  * Machine Learning Pipeline: `scikit-learn`, `xgboost` 🤖
* **Defensive Coding:** Standardized robust data loading wrapped in `try-except` blocks to handle file path exceptions cleanly.
* **Business Intelligence & Analytics:** `Power BI` 📈 (Created interactive dashboards via Power BI Service / Semantic Modeling using custom DAX formulations)

---

## 🛠️ Machine Learning Pipeline & Results

### 📊 Validation Set Performance Standings (Deduplicated Dataset)

| Model Classifier | Accuracy (Baseline) | Precision / Recall (Class 1) | Strategic Note |
| :--- | :---: | :---: | :--- |
| **Logistic Regression** | 78.81%* | 66% / 47% | Requires feature scaling beforehand. |
| **Random Forest** | 84.15% | 75% / 64% | Excellent balance of detecting cancellations and avoiding false alarms. |
| **XGBoost** | 84.02% | 74% / 65% | **Selected Model.** Minimal higher recall makes it slightly better for overbooking strategies. |

*(Note: No hyperparameter tuning was performed in this iteration).*

---

## 📝 My Monthly Reflection: June 2026

### 🚀 What went well?
* Effectively utilizing Python's Pandas library, which has made data manipulation significantly more accessible than I initially anticipated.
* Setting up the comparative analysis pipeline (V2) to clearly demonstrate the impact of data deduplication on model outcomes.

### 🧠 Key Learnings
* **Classification Report:** I learned that pure Accuracy can be misleading. Instead, I now understand how to balance Precision (minimizing false alarms) and Recall (finding actual cancellations) depending on the business goals.
* **Model Differences:**
  * **Logistic Regression:** Calculates probabilities based on feature weights. Crucial step: The data must be scaled beforehand.
  * **Random Forest:** Multiple trees make decisions simultaneously and independently.
  * **XGBoost:** Works sequentially. One tree learns from the mistakes of the previous tree and tries to fix them in the next step.

### 🔄 What would I do differently next time?
* Explore strategies for handling imbalanced classes, as cancellations might represent a smaller fraction of the dataset after deduplication.

---

### 🔮 Next Month's Goals (July 2026)
1. **SQL Integration via VS Code:** Establish a seamless database workflow by connecting and executing SQL queries directly within the VS Code environment to handle larger, relational data structures.
2. **Advanced Functional Programming & Error Handling:** Refactor repetitive code into modular Python functions to improve efficiency, while implementing defensive programming techniques (like validation checks and error handling) to minimize runtime failures.