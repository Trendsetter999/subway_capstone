# Capstone2
# NYC Subway Ridership Prediction — Capstone Project

**Author:** Joe Todaro  
**Last Updated:** October 2025  

---

## Project Overview
This project builds a **machine learning pipeline** to forecast **daily subway station ridership** in New York City using **MTA Hourly Ridership** data and **U.S. Federal Holidays** as contextual features.  

The analysis follows the **CRISP-DM framework** — covering business understanding, data preparation, modeling, evaluation, and deployment readiness — and applies professional data science practices such as version control, modular pipeline design, and reproducibility.

The project demonstrates:
- **Data engineering** from raw hourly entries → daily ridership per station  
- **Feature creation** for calendar and holiday effects  
- **Predictive modeling** using Random Forest Regression  
- **Evaluation** of temporal stability using rolling backtests  
- **Model interpretability** through visual summaries and KPI metrics  

---

## Data Sources

| Dataset | Description | Source |
|----------|--------------|--------|
| **MTA Subway Hourly Ridership (Beginning Feb 2022)** | Hourly entry counts by station | Kaggle / NYC Open Data |
| **U.S. Federal Holidays** | Calendar of U.S. federal holidays | Kaggle / US Gov Data |
| *(Optional)* MTA Daily Ridership | Used for validation only | Kaggle |

---

## CRISP-DM Framework Alignment

| Phase | Description | Key Deliverables |
|-------|--------------|------------------|
| **1. Business Understanding** | Define goal: forecast daily ridership for staffing & planning optimization. | Project Pitch (.docx) |
| **2. Data Understanding** | Inspect and profile MTA and holiday datasets. | Notebook 00 |
| **3. Data Preparation** | Clean, aggregate, and merge hourly ridership with holidays. | Notebook 01 |
| **4. Modeling** | Train/test multiple regressors (Linear, Random Forest, optional XGBoost). | Notebook 02 & 03 |
| **5. Evaluation** | Evaluate MAE, RMSE, R²; perform rolling backtests for stability. | Notebook 03 |
| **6. Deployment** | Prepare processed datasets and artifacts for presentation. | Processed `.csv` outputs |

---

## Repository Structure

subway_capstone/
│
├── data/
│ ├── raw/
│ │ └── turnstile/
│ │ ├── MTA_Subway_Hourly_Ridership__Beginning_February_2022.csv
│ │ ├── federal_holidays.csv
│ │ └── (optional) MTA_Daily_Ridership.csv
│ │
│ ├── interim/
│ │ └── (temporary cleaned files)
│ │
│ └── processed/
│ ├── station_day.csv
│ ├── kpi_overall_test.csv
│ ├── station_mae_test.csv
│ ├── dow_mae_test.csv
│ ├── holiday_mae_test.csv
│ └── predictions_test.csv
│
├── notebooks/
│ ├── 00_data_build_station_day.ipynb # Load, clean, aggregate hourly data
│ ├── 01_eda_and_visuals.ipynb # Exploratory Data Analysis & initial visuals
│ ├── 02_model_pipeline.ipynb # Feature engineering + baseline model build
│ └── 03_modeling_evaluation.ipynb # Final modeling, backtests, and KPIs
│
├── .gitignore
├── README.md
