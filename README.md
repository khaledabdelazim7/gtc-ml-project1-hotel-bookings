🏨 GTC ML Project 1 - Data Cleaning & Preprocessing Challenge
📌 Objective

The goal of this project is to build a robust data preprocessing pipeline for a hotel booking cancellation prediction model.
While the final model is not part of this project, the quality of data cleaning and preprocessing will directly determine the future model’s performance.

📊 Business Problem

The Revenue Team has identified that last-minute booking cancellations significantly impact profitability. By preparing a clean, machine-learning-ready dataset, we can enable the development of accurate models that predict cancellations in advance—helping hotels optimize operations and reduce losses.

📁 Dataset

Source: Raw dataset from the Property Management System (PMS).

File: hotel_bookings.csv

Target variable (for future modeling): is_canceled

🔎 Project Workflow
Phase 1: Exploratory Data Analysis (EDA) & Data Quality Report

Loaded data and generated summary statistics (.describe(), .info()).

Identified missing values with visualizations (missingno matrix / heatmap).

Detected outliers in key columns (adr, lead_time) using boxplots + IQR method.

Documented findings on missing values, duplicates, outliers, and data types.

Phase 2: Data Cleaning

Handle Missing Values

company, agent: filled with 0 (or "None").

country: imputed with the mode or "Unknown".

children: imputed with median.

Remove Duplicates

Dropped exact duplicate rows.

Handle Outliers

adr: capped at 1000 to reduce skew.

Other numerical outliers handled with IQR-based capping.

Fix Data Types

Converted date columns into datetime format.

Phase 3: Feature Engineering & Preprocessing

New Features

total_guests = adults + children + babies

total_nights = stays_in_weekend_nights + stays_in_week_nights

is_family = 1 if (children > 0 or babies > 0) else 0

Categorical Encoding

One-Hot Encoding for low-cardinality features (meal, market_segment, etc.).

Frequency encoding or grouping rare categories for high-cardinality features (country).

Data Leakage Prevention

Dropped reservation_status and reservation_status_date.

Final Dataset Preparation

Train-test split: train_test_split(test_size=0.2, random_state=42).

✅ Deliverables

Cleaned dataset: Machine-learning-ready, free of duplicates, missing values, and outliers.

EDA & Data Quality Report: Summary of insights, issues, and cleaning decisions.

Preprocessing Pipeline: Reproducible steps to prepare raw hotel booking data for modeling.

🛠️ Tools & Libraries

Python 3.10+

Pandas, NumPy (data manipulation)

Matplotlib, Seaborn, Missingno (visualization)

Scikit-learn (preprocessing, train-test split)

🚀 Next Steps

Use this cleaned dataset to build predictive models for hotel booking cancellations.

Compare classical ML (Random Forest, XGBoost) vs. deep learning models (LSTM).

Deploy the best-performing model into a hotel management dashboard.

📂 Project Structure
GTC-ML-Project1/
│── data/
│   └── hotel_bookings.csv
│── notebooks/
│   └── hotel_bookings.ipynb
│── outputs/
│   └── cleaned_hotel_bookings.csv
│── README.md

👨‍💻 Author

Khaled Abdelazim
