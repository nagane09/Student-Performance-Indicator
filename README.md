# Student Performance Indicator

🔗 **Live Demo:** https://student-performance-indicator-3.onrender.com/

---

# 🎓 Student Performance Indicator (End-to-End ML Project)

This project predicts a student’s **Math Score** based on demographic and academic features using **Machine Learning regression models**.  
It implements a **complete end-to-end ML pipeline**, including data ingestion, transformation, model training, evaluation, and deployment using **Flask**.

---

## 📌 Problem Statement

Student academic performance is influenced by multiple social and educational factors.  
This project aims to **predict the Math Score** of a student using features such as:

- Gender
- Race/Ethnicity
- Parental level of education
- Lunch type
- Test preparation course
- Reading score
- Writing score

This is a **supervised regression problem**.

---

## 🧠 Solution Overview

The solution follows **production-level ML architecture**:

1. Data Ingestion
2. Data Transformation
3. Model Training & Hyperparameter Tuning
4. Model Evaluation
5. Model Persistence
6. Prediction Pipeline
7. Flask Web Application

---

## 📊 Dataset Information

- **Source**: Kaggle – Students Performance in Exams
- **Target Variable**: `math_score`
- **Features**:
  - Categorical: gender, race_ethnicity, parental_level_of_education, lunch, test_preparation_course
  - Numerical: reading_score, writing_score

---

## 🧹 Data Ingestion

- Reads raw dataset from:   notebook/data/stud.csv
- Splits data into:
- 80% Training set
- 20% Test set
- Saves artifacts: artifacts/data.csv, artifacts/train.csv, artifacts/test.csv

---

## 🔄 Data Transformation

Implemented using **Scikit-learn Pipelines & ColumnTransformer**.

### Numerical Features
- Median Imputation
- Standard Scaling

### Categorical Features
- Most-frequent Imputation
- One-Hot Encoding
- Standard Scaling (`with_mean=False`)

### Saved Artifact:-  artifacts/preprocessor.pkl

---

## 🤖 Model Training & Selection

Multiple regression models are trained and evaluated using **GridSearchCV**:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- AdaBoost Regressor
- XGBoost Regressor
- CatBoost Regressor

### Evaluation Metric
- **R² Score**

The best-performing model (based on test R²) is:
- Automatically selected
- Saved as:-  artifacts/model.pkl


---

## 📈 Model Evaluation

- Models are evaluated on both training and test datasets
- Overfitting is controlled via:
  - Cross-validation
  - Hyperparameter tuning
- If the best model score is below **0.6**, training fails safely

---

## 🔮 Prediction Pipeline

During inference:

1. User inputs data via the Flask UI
2. Inputs are converted into a Pandas DataFrame
3. Preprocessing is applied using saved `preprocessor.pkl`
4. Trained model predicts the **Math Score**

---

## 🌐 Flask Web Application

The Flask app provides a clean UI for prediction.

### App Capabilities
- Collects user inputs via HTML forms
- Executes preprocessing + prediction pipeline
- Displays predicted Math Score

### Routes
- `/` → Landing page
- `/predictdata` → Prediction form and output

---


---

## 🧾 Logging & Exception Handling

- Centralized logging system with timestamped log files
- Custom exception handling with:
  - File name
  - Line number
  - Error message
- Improves debuggability and production readiness

---

## 🛠️ Tech Stack

- **Programming**: Python
- **ML**: Scikit-learn, XGBoost, CatBoost
- **Data**: Pandas, NumPy
- **Deployment**: Flask
- **Utilities**: GridSearchCV, Pickle
- **Version Control**: Git, GitHub

---

## 🚀 Future Enhancements

- Add MAE and RMSE metrics
- Introduce SHAP-based explainability
- Dockerize the application
- Add CI/CD pipeline
- Deploy on AWS / GCP / Render





