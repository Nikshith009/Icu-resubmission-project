# Icu-resubmission-project
An explainable machine learning system using CatBoost to predict ICU readmission risk. Includes SMOTE-Tomek balancing, SHAP &amp; LIME for interpretability, and a real-time input interface. Designed to support safer ICU discharge decisions and reduce preventable readmissions
📘 Explainable Machine Learning Model for ICU Readmission Risk Prediction

A CatBoost-based interpretable ML system for predicting ICU readmission using SHAP & LIME

🚀 Overview

ICU readmission is a major challenge in hospitals, often linked to preventable complications, increased mortality, and resource strain.
This project presents an explainable machine learning system that predicts ICU readmission within 30 days using a real-world hospital dataset.

The model uses:
✔ CatBoost → Handles categorical features & delivers strong performance
✔ SMOTE-Tomek → Fixes class imbalance for better detection of high-risk cases
✔ SHAP & LIME → Provides global & local interpretability
✔ Real-Time Interface → Allows users (clinicians/operators) to input patient data and view transparent predictions

🧠 Key Features

CatBoost Classifier trained on 25,000 patient records

Balanced training using SMOTE-Tomek for improved recall

Explainable predictions using SHAP summary plots & LIME local explanations

ROC-AUC: 0.66 and Recall: 0.68 – critical in medical predictions

CLI / Streamlit app for instant risk prediction

Interpretable insights into the factors influencing readmission

📊 Dataset

The project uses a preprocessed version of the Diabetes 130-US Hospitals Dataset, containing:

Patient demographics

Lab procedures

Medications

Diagnosis codes

Inpatient/Outpatient history

A1Ctest & glucose test results

Readmission indicator (target variable)

17 selected features were used after cleaning and encoding.

🏗️ System Architecture
1️⃣ Data Preprocessing

Removed irrelevant fields (IDs, inconsistent entries)

Encoded categorical features

Normalized numerical values

Converted readmission into a binary classification label

2️⃣ Handling Class Imbalance

Used SMOTE-Tomek to:

Oversample minority cases

Remove noisy border points

Improve sensitivity to high-risk patients

3️⃣ Model Training (CatBoost)

Hyperparameters tuned via Grid Search:

Depth

Learning Rate

L2 Regularization

Number of Estimators

Train-test split → 80:20

4️⃣ Model Explainability

SHAP

Identifies top features: inpatient visits, A1C test, emergency visits, meds, hospital stay

Visualizes global & per-patient contributions

LIME

Local explanations for individual predictions

Helps clinicians understand each decision

5️⃣ Real-Time Interface

A simple interactive system where users can:

Enter patient data

Get a prediction score

View SHAP & LIME interpretability visualizations

📈 Results
✔ Performance Metrics
Metric	Value
Accuracy	0.62
Precision	0.63
Recall	0.68
F1-Score	0.65
ROC-AUC	0.66
✔ Confusion Matrix

The model correctly predicted 1348 high-risk patients and significantly reduced false negatives.

✔ Important Insights

Higher number of inpatient/emergency visits is strongly linked to readmission

Abnormal A1C test results increase risk

Medication changes during the stay strongly influence outcomes

🌐 Live Demo

Streamlit App:
👉 https://icu-readmission-project.streamlit.app/

🛠️ Tech Stack

Python

Pandas / NumPy

CatBoost

Imbalanced-learn (SMOTE-Tomek)

SHAP & LIME

Matplotlib / Seaborn

Streamlit

📌 Project Structure
📁 ICU-Readmission-ML
│── data/
│── models/
│── notebooks/
│── src/
│   ├── preprocess.py
│   ├── train.py
│   ├── explain.py
│   ├── interface.py
│── README.md
│── requirements.txt
│── app.py (Streamlit app)

🔮 Future Enhancements

Integrate into hospital EHR systems

Add time-series vitals using LSTMs

Build a fully interactive web dashboard

Expand dataset to multiple hospitals

Add fairness & bias evaluation mechanisms

Automate periodic retraining

📝 Conclusion

This project delivers a robust, interpretable ICU readmission prediction system that balances accuracy with transparency—critical for real-world medical use.
By combining CatBoost, SMOTE-Tomek, SHAP, and LIME, the model supports clinicians in making safer discharge decisions and reducing preventable ICU readmissions.
