# Student Performance Indicator

🔗 **Live Demo:** https://student-performance-indicator-3.onrender.com/

---

# **Student Performance Prediction Using Machine Learning**

## **Abstract**

Predicting student performance enables early identification of at-risk students and supports data-driven educational interventions. This project implements an **end-to-end machine learning pipeline** to predict **students’ final math scores** based on demographic, socio-economic, and academic features. Multiple regression models were evaluated, and **Linear Regression emerged as the best-performing model with 87.9% accuracy**. The pipeline includes preprocessing, model training, evaluation, and deployment via a Flask web interface.

**Key contributions:**

* End-to-end ML pipeline for regression tasks  
* Comparative analysis of multiple machine learning models  
* Preprocessing pipeline for handling numerical and categorical data  
* Real-time prediction capability via Flask  

---

## **1. Problem Statement**

Given a set of student features:

X = { gender, race_ethnicity, parental_education, lunch, test_preparation, reading_score, writing_score }

Predict the final math score:

y_pred = f(X; theta), where y is a real number
where \(f\) is a regression model and \(\theta\) are the model parameters.

---

## **2. Dataset**

* **Source:** Publicly available student performance dataset  
* **Records:** ~1000+  
* **Features:**

| Feature                     | Description                   |
| --------------------------- | ----------------------------- |
| gender                      | Male/Female                   |
| race_ethnicity              | Group A–E                     |
| parental_level_of_education | Highest education of parent   |
| lunch                       | Standard / Free               |
| test_preparation_course     | Completed / None              |
| reading_score               | Reading exam score            |
| writing_score               | Writing exam score            |
| math_score                  | Target variable (final score) |

* **Train/Test Split:** 80%/20%  
* **Missing Values:** Imputed using median (numerical) and most frequent (categorical)  

---

## **3. Data Preprocessing**

* **Numerical Features:** `reading_score`, `writing_score`  
  * Imputation: Median  
  * Scaling: StandardScaler  

* **Categorical Features:** `gender`, `race_ethnicity`, `parental_level_of_education`, `lunch`, `test_preparation_course`  
  * Imputation: Most frequent value  
  * Encoding: One-Hot Encoding  
  * Scaling: StandardScaler (with_mean=False)  

* **Pipeline:** Preprocessing performed via **ColumnTransformer** for reproducibility  
* **Artifact Saved:** `preprocessor.pkl` for real-time predictions  

---

## **4. Models Considered**

Seven regression models were trained and evaluated. A brief explanation of each:

| Model                       | Description & Use Case                                                                 |
| --------------------------- | ------------------------------------------------------------------------------------ |
| **Linear Regression**       | Simple linear model; predicts outcome as weighted sum of features. Best for linear relationships and interpretable results. |
| **Decision Tree Regressor** | Non-linear tree-based model; captures feature interactions. Useful for datasets with complex non-linear patterns. |
| **Random Forest Regressor** | Ensemble of decision trees; reduces overfitting and improves generalization. Good for high-dimensional, noisy data. |
| **Gradient Boosting Regressor** | Sequential ensemble that improves weak learners iteratively. Works well for structured data with complex patterns. |
| **AdaBoost Regressor**      | Boosting of weak learners; focuses on difficult-to-predict points. Often used for small- to medium-sized datasets. |
| **XGB Regressor**           | Optimized gradient boosting; fast and accurate, often used in competitions and large datasets. |
| **CatBoost Regressor**      | Gradient boosting specialized for categorical features; reduces preprocessing effort. |

✅ **Observation:** After training and hyperparameter tuning, **Linear Regression achieved the best performance** with **87.9% accuracy**, indicating strong linear correlation between reading/writing scores and final math score.

---

## **5. Evaluation Metrics**

* **Mean Squared Error (MSE):**

MSE = (1/n) * Σ (y_i - y_pred_i)^2

* **Mean Absolute Error (MAE):**

MAE = (1/n) * Σ |y_i - y_pred_i|

* **R² Score:**

R² = 1 - [ Σ (y_i - y_pred_i)^2 / Σ (y_i - y_mean)^2 ]

* **Accuracy** (rounded prediction):

Accuracy = (Number of correct predictions (rounded) / Total predictions) * 100

---

## **6. Pipeline Overview**

**Steps:**

1. **Data Ingestion** → Load CSV data  
2. **Preprocessing** → Imputation, scaling, encoding  
3. **Model Training** → Train all 7 models  
4. **Evaluation** → Compute R², MSE, MAE, Accuracy  
5. **Model Selection** → Linear Regression selected as best  
6. **Persistence** → Save `model.pkl` and `preprocessor.pkl`  
7. **Deployment** → Flask app for real-time predictions  

---

## **7. Deployment**

* **Framework:** Flask Web Application  
* **Functionality:**  
  * Users input student features  
  * Data transformed using `preprocessor.pkl`  
  * Model predicts `math_score`  
  * Prediction returned via web interface  

---

## **8. Conclusion**

This project demonstrates:

* Preprocessing of numerical and categorical features  
* Training and evaluation of seven regression models  
* **Linear Regression achieved best performance with 87.9% accuracy**  
* Deployment pipeline enables real-time prediction  

**Future Work:**  

* Explore stacking or ensemble methods to improve performance  
* Incorporate additional features (attendance, participation, homework scores)  
* Add interpretability using **SHAP** or **LIME**  

