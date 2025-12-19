"# Student-Performance-Indicator" 


https://student-performance-indicator-3.onrender.com/

# Student Performance Indicator

🔗 **Live Demo:** https://student-performance-indicator-3.onrender.com/ :contentReference[oaicite:1]{index=1}

---

## 📌 Project Overview

The **Student Performance Indicator** is a machine learning‑driven web application that predicts a student’s academic performance based on their demographic, social, and educational attributes.

The goal of this project is to help educators, parents, and students **identify potential performance outcomes**, enabling early interventions and support where needed.

This system combines **data preprocessing**, **machine learning classification**, and a **user‑friendly web interface** to deliver accurate predictions in real time.

---

## 🧠 What It Does

Given student inputs such as:
* Gender  
* Ethnicity  
* Parental level of education  
* Lunch type  
* Test preparation course completion  
* Math score  
* Reading score  
* Writing score  

The app predicts whether the **student will perform well academically**.

Users interact with the system through the web UI by entering their features and receiving a performance prediction instantly.

---

## 📁 Project File Structure & Purpose

| File / Folder | Purpose |
|---------------|---------|
| **`app.py`** | Entry point for the web application. Loads the trained model and preprocessing pipeline, takes user input from the web form, and displays predictions. |
| **`requirements.txt`** | Lists all Python packages required to run the project locally (Flask, scikit-learn, pandas, etc.). |
| **`setup.py`** | Optional script for installing the project as a package. Helps manage dependencies and project setup. |
| **`artifacts/`** | Contains serialized model files (e.g., `.pkl` or `.joblib`) and preprocessing objects needed to make predictions. |
| **`catboost_info/`** | Metadata folder generated if CatBoost is used; contains training info, tree structure, and model logs. |
| **`notebook/data/`** | Contains the datasets used for training/testing and performing exploratory data analysis (EDA). |
| **`src/`** | Source code folder containing helper modules: |
| `src/data.py` | Handles data loading and preprocessing functions. |
| `src/model.py` | Contains code to train, evaluate, and save machine learning models. |
| `src/pipeline.py` | Builds the end-to-end pipeline: preprocessing + model prediction. |
| **`templates/`** | HTML templates for the Flask web app, providing the user interface. |
| **`README.md`** | Documentation for the project: explains purpose, usage, results, and file structure. |

> **Notes:**  
> - `artifacts/` and `catboost_info/` are automatically generated after model training.  
> - The `src/` folder is modular, so new preprocessing steps or models can easily be added.  
> - `templates/` allows UI customization without modifying Python code.

---
## 🛠 Technologies Used

* **Python** – Primary development language  
* **Flask** – Backend API and web framework  
* **scikit‑learn / CatBoost / Other ML libs** – Machine learning modeling  
* **HTML/CSS** – Frontend UI  
* **Joblib or Pickle** – Model serialization  
* **CSV Files** – Input dataset format





