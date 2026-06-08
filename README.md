
# 🚀 Kaggle Data Science & Machine Learning Challenges

Welcome to my portfolio of Kaggle competitions and data science challenges. This repository is dedicated to showcasing structured machine learning pipelines, robust feature engineering, and production-ready clean code.

My primary focus across these projects is enforcing strict **Leakage-Free Validation** using Scikit-Learn `Pipelines` and advanced cross-validation techniques, ensuring that models reflect true real-world performance.

---

## 📌 Project Overview

| # | Challenge & Dataset | Directory | Key Technical Focus | Status |
| :--- | :--- | :--- | :--- | :--- |
| **01** | **Titanic: Machine Learning from Disaster** | [`./01_Tabular_Titanic`](./01_Tabular_Titanic) | Custom Transformers, KDE-based Feature Engineering, Leak-free `GridSearchCV` | **Completed** |
| **02** | **House Prices: Advanced Regression Techniques**| [`./02_Tabular_House_Prices`](./02_Tabular_House_Prices) | Advanced Imputation, Target Transformation, Ensemble Learning | *Upcoming* |

---

## 🛠️ Core Engineering Principles

To maintain professional-grade data science standards, every solution in this repository strictly adheres to the following workflow:

1. **Strict Train-Validation Isolation:** Data splits are executed immediately upon raw data ingestion. Validation folds are kept completely locked away until model evaluation.
2. **Object-Oriented Feature Engineering:** All preprocessing steps (imputation, scaling, categorical encoding, and custom domain-specific transformations) are wrapped into custom `scikit-learn` estimators via `BaseEstimator` and `TransformerMixin`.
3. **Unified Pipelines:** Feature pipelines and classifiers are bundled into a cohesive `Pipeline` object, forcing all mathematical dependencies (e.g., global metrics, KDE densities) to evaluate dynamically *inside* each cross-validation fold to prevent data leakage.
4. **Group Permutation Importance:** Model explanations are evaluated using feature-group shuffling post-OneHotEncoding to prevent structural bias and misinterpretation of categorical feature weights.

---

## 📈 Featured Highlight: Titanic Pipeline Implementation

In the **Titanic** challenge, instead of applying global preprocessing to the entire training set (a common pitfalls causing data leakage), I designed an isolated execution pipeline:

* **Custom KDE Age Categorizer:** Dynamically computes Kernel Density Estimate (KDE) intersections between survival targets *exclusively on training folds* to find un-leaked age boundaries (Child vs. Adult).
* **Robust Cross-Validation:** Utilized 5-fold cross-validation wrapped inside `GridSearchCV` over the full pipeline, reducing the generalization error gap between local validation scores and the actual Kaggle leaderboard.

---

## 🧰 Tech Stack
* **Languages:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, SciPy, Matplotlib, Seaborn
* **Methodologies:** Grid Search CV, Pipeline Architecture, Feature Importance, Exploratory Data Analysis (EDA)

---
*Feel free to explore the directories to review the implementations, notebooks, and architectural design patterns.*
