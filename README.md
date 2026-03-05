# ⚡ Energy Load Forecasting for PJM Interconnection

A machine learning–based time series forecasting project for predicting hourly electricity demand across multiple companies within the PJM Interconnection.
This repository contains the full data processing, feature engineering, modeling, and evaluation pipeline used to train a global tree-based regression model for energy load prediction.


## 📌 Project Objective
The goal of this project is to build a robust forecasting model capable of:
📈 Learning seasonal load patterns (hourly, daily, yearly)
🔄 Capturing similarities across multiple PJM companies
🌍 Generalizing using a single global model
📊 Producing stable and interpretable regression performance
Instead of training separate models per company, a unified global model is used with the company treated as a categorical feature.


## 🧠 Modeling Approach
This project implements a global supervised regression framework using:
🌲 Tree-based regression model
🏷 Company encoded as a categorical feature
⏳ Lag features for temporal dependency learning
📊 Rolling statistics (moving averages, trend features)
📅 Chronological train-test split (no data leakage)
📐 Log-transformed target for scale stabilization
The model is trained on historical load data and evaluated on a held-out test period.


## 📊 Evaluation Metrics
Model performance is evaluated using:
Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)
R² Score
These metrics assess both absolute error magnitude and the model’s ability to explain variance in energy demand.


## 📂 Repository Structure
Data preprocessing and cleaning scripts
Feature engineering pipeline
Model training and evaluation notebooks
Utility functions
Saved model artifacts


## 🧰 Tech Stack
Python
Pandas & NumPy
Scikit-learn
Tree-based models (e.g., XGBoost / LightGBM / Random Forest)


## 💡 Key Design Decision — Global Model
A global model was chosen instead of per-company models in order to:
Leverage shared seasonal demand patterns
Improve generalization across zones
Reduce modeling complexity
Enable scalable multi-company forecasting


⚠️ Note on Forecasting Horizon
Forecast reliability decreases as the prediction horizon extends further beyond the training period. Long-term forecasts should be interpreted with caution due to increasing uncertainty.
