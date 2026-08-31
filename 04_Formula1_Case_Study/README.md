# Formula 1 World Championship Analysis

This project is part of my **Data Analytics & Machine Learning journey** and focuses on analyzing historical Formula 1 data from 1950 to 2024.

The project combines Exploratory Data Analysis, Feature Engineering and Machine Learning to investigate historical race patterns and predict race wins.

---

## 🔄 Project Pipeline & Structure

### 🔹 1. Exploratory Data Analysis (EDA)

Exploring historical Formula 1 data to identify:

- Race and driver statistics
- Constructor performance
- Circuit and country patterns
- Pole position and race wins
- Position changes
- Historical trends

### 🔹 2. Feature Engineering & Pre-Processing

Preparing the data for machine learning by:

- Combining multiple CSV datasets
- Creating historical driver performance features
- Creating historical constructor performance features
- Creating `pole_position`
- Handling missing values
- Preventing data leakage through time-based feature creation

### 🔹 3. Machine Learning Model Training

Building classification models to predict whether a driver wins a race.

Models used:

- Dummy Classifier
- Random Forest Classifier
- Gradient Boosting Classifier

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

Hyperparameter optimization and classification threshold optimization were also applied.

---

## ⚙️ Tech Stack & Tools

- **Language:** Python
- **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn
- **Environment:** Jupyter Notebook, Kaggle
- **Visualization:** Matplotlib, Seaborn

---

## 🛠️ Machine Learning Pipeline & Results

The machine learning workflow uses a chronological train/test split:

- **Training:** 1950–2019
- **Testing:** 2020–2024

Because race wins represent only a small proportion of the dataset, the project focuses particularly on **Precision, Recall and F1-score** for the winning class rather than relying solely on accuracy.

Threshold optimization was used to improve the balance between precision and recall.

The final model comparison will evaluate Random Forest and Gradient Boosting based on their performance on unseen race data.

---

## 📝 My Monthly Reflection: August 2026

### 🚀 What went well?

- Completed a full Formula 1 project from EDA through Feature Engineering to Machine Learning.
- Worked with multiple related CSV datasets and practiced merging data from different sources.
- Applied Random Forest and Gradient Boosting.
- Practiced hyperparameter optimization using GridSearchCV.
- Learned how classification thresholds can influence precision, recall and F1-score.

### 🧠 Key Learnings

This project helped me understand that building a machine learning model is more than simply fitting an algorithm.

I learned the importance of:

- Understanding the data before modeling
- Creating meaningful features
- Preventing data leakage
- Choosing an appropriate train/test strategy
- Evaluating imbalanced classification problems correctly
- Comparing multiple models
- Understanding the effect of hyperparameters
- Interpreting model results instead of focusing only on accuracy

At the same time, I realized that I still need to strengthen my understanding of the underlying concepts. My goal is to move away from simply implementing code and towards being able to clearly explain **why each step is necessary and what it does**.

### 🔄 What would I do differently next time?

For future projects, I want to spend more time understanding each step before implementing it.

I also want to:

- Experiment more independently
- Compare different approaches systematically
- Spend more time interpreting the results

---

## 🔮 Next Month's Goals (September 2026)

1. **Strengthen my understanding of SQL**
2. **Continue practicing hyperparameter tuning**
3. **Learn and apply Power BI for data visualization**
4. **Work on another project using multiple datasets and merge techniques**
