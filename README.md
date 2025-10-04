### Early-Readmission-Risk-Prediction-in-Diabetic-Patients
 # 📌 Project Overview

This project predicts whether diabetic patients will be readmitted within 30 days of discharge using machine learning. Early readmissions increase costs and impact patient health outcomes. By identifying high-risk patients, hospitals can provide targeted interventions, reduce complications, and improve care quality.

# 📊 Dataset

Source: Diabetes 130-US hospitals dataset (1999–2008)

Size: ~100,000 patient records

Features: 47 attributes including demographics, admission details, lab results, medications, diagnoses, and discharge information

Target Variable: readmitted_numerical

1 → Readmitted within 30 days

0 → Not readmitted

# ⚙️ Data Preprocessing

Removed duplicates and irrelevant identifiers (encounter_id, patient_nbr).

Handled missing values (medical_specialty, payer_code).

Applied One-Hot Encoding for categorical variables (age, insulin, medical_specialty, etc.).

Scaled numerical features (time_in_hospital, num_lab_procedures, etc.) using StandardScaler.

Addressed class imbalance with:

Class weighting

SMOTE oversampling (tested but limited improvement)

# 📈 Exploratory Data Analysis (EDA)

Here are key insights and graphs from EDA:

Distribution of Readmissions


Age vs Readmission


Hospital Stay vs Readmission


Correlation Heatmap (Spearman)


Feature Importance (Random Forest)


# 🤖 Models Implemented

We compared multiple models for classification:

Logistic Regression

Decision Tree

Random Forest

LightGBM

K-Nearest Neighbors (KNN)

LSTM (Neural Network)

# 📉 Results
Model	Accuracy	Recall (Class 1)	Precision (Class 1)	F1-Score (Class 1)	AUC
Logistic Regression	81%	28%	23%	25%	~0.70
Decision Tree	83%	23%	23%	23%	~0.71
LightGBM	84%	21%	24%	23%	~0.74
KNN (k=7)	46%	65%	13%	21%	~0.55
LSTM	60%	61%	58%	60%	~0.78

👉 Best Model: LSTM — despite lower accuracy, it achieved the highest recall for Class 1 (readmitted), which is crucial in healthcare.


# 📌 Future Improvements

Explore advanced deep learning models (GRU, Transformer-based).

Incorporate temporal data such as sequence of patient visits.

Use SHAP/LIME for better interpretability of high-risk patient predictions.
